pipeline{
        agent any
        stages{
            stage('Clean'){
                steps{
                    sh label: '', script: '''if [ "$(docker ps -aq -f name=jordangrindrod/chaperoo-client)" ]; then
                        docker rm -f jordangrindrod/chaperoo_client
                    fi'''
                    }
                }
            stage('Build Images'){
                steps{
                    sh "docker build -t jordangrindrod/chaperoo-client ."
                }
            }
            stage('Push Image'){
                steps{
                    sh "docker push jordangrindrod/chaperoo-client"
                }
            }
            stage('Run App'){
                steps{
                    sh "docker-compose up -d"
                }
            }
        }    
}
