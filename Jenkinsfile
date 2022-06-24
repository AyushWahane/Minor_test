pipeline {
    environment {
        registry = "krishna1708/minor_test1"
        registryCredential = ''
        dockerImage = ''
    }
    agent any
    stages {
        stage('Clone Git Repo') {
            steps{
                sh """
                    git clone https://github.com/AyushWahane/Minor_test.git
                    
                """
            }
        }   
        stage('Building image') {
            steps{
                sh """
                    cd Minor_test
                    docker login -u krishna1708 -p Abcd97@4321
                    docker build -t krishna1708/minor_test1:latest .
                """
            }
        }
        
        
        stage('Push image') {
            steps{
                sh """
                    docker login -u krishna1708 -p Abcd97@4321
                    docker push krishna1708/minor_test1:latest
                """
            }
        }
        
        stage('Cleaning up') {
            steps{
                sh """
                    docker rmi krishna1708/minor_test1:latest
                """
            }
        }
    }
}
