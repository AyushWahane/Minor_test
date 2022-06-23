pipeline {
    environment {
        registry = "krishna1708/minor_test1"
        registryCredential = ''
        dockerImage = ''
    }
    agent any
    stages {
        stage('Clone') {
            steps{
                sh """
                    git clone https://github.com/AyushWahane/Minor_test.git
                    
                """
            }
        }   
        stage('Building our image') {
            steps{
                sh """
                    cd Minor_test
                    docker login -u krishna1708 -p Abcd97@4321
                    docker build -t krishna1708/minor_test1:$BUILD_NUMBER .
                    
                """
            }
        }
        
        
        stage('Push our image') {
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
