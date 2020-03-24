pipeline{
        agent any
        stages{
            stage('Clean'){
                steps{
                    sh label: '', script: '''if [ "$(sudo docker ps -aq -f name=jordangrindrod/chaperoo-client)" ]; then
                        sudo docker rm -f jordangrindrod/chaperoo_client
                    fi'''
                    }
                }
            stage('Build Image'){
                steps{
                    sh "sudo docker build -t jordangrindrod/chaperoo-client ."
                }
            }
            stage('Run App'){
                steps{
                    sh "sudo docker-compose up -d"
                }
            }
        }    
}
