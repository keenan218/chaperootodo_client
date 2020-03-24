pipeline{
        agent any
        stages{
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
