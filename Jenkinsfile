pipeline{
        agent any
        stages{
            stage('Clean'){
                steps{
                    sh label: '', script: '''
                    if [ "$(sudo docker images name=jordangrindrod/chaperoo-client)" ]; then
                        sudo docker rmi jordangrindrod/chaperoo_client -q
                    fi
                    '''
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
