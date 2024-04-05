pipeline {
    agent any
    
    environment {
        SCANNER_HOME=tool 'sonar-server'
    }
    stages {
        stage('clean workspace') {
            steps {
                cleanWs()
            }
        }
        stage('Checkout from Git') {
            steps {
                git branch: 'main', url: '<github_url>'  
            }
        }
        stage('TRIVY FS SCAN') {
            steps {
                sh "trivy fs --format table -o trivy-fs-report.html ."
            }
        }
        stage("Sonarqube Analysis ") {
            steps {
                withSonarQubeEnv('sonar') {
                    sh ''' $SCANNER_HOME/bin/sonar-scanner -Dsonar.projectName=stock price  analysis \
                    -Dsonar.projectKey=stock price analysis '''
                }
            }
        }

        stage("Docker Build & Tag image") {
            steps {
                script {
                   withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {   
                       sh "docker build -t <dockerhub_name/image_name .>"
                    }
                }
            }
        }
        stage("TRIVY") {
            steps {
                sh "trivy image --format json -o trivy-image-report <dockerhub_name/image_name:<tag>>"
            }
        }

        stage("Docker Push image") {
            steps {
                script {
                   withDockerRegistry(credentialsId: 'docker', toolName: 'docker') {   
                       sh "docker push <dockerhub_name/image_name:<tag>>"
                    }
                }
            }
        } 
        stage('Deploy to Container') {
            steps {
               sh "docker run -d -p 8081:80 <dockerhub_name/image_name:<tag>>"
            }
        }
        stage('Deployment Done') {
            steps {
                echo 'Deployment done'
            }
        }
    }
    post {
        success {
            echo 'Build and deployment successful!'
        }
        failure {
            echo 'Build or deployment failed!'
        }
        always {
             echo "Stock Price Analysis Project"
        }
    }
}
