// Jenkinsfile by Lawrence
pipeline {
    agent any

    stages {
        stage('Git checkout') {
            steps{
                // Get source code from a GitHub repository
                git branch:'main', url:'https://github.com/liwenbo55/p3_Techscrum.fe.git'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
        
    post {
        success {
            emailext(
                subject: "Jenkins Pipeline succeeded.",
                body: "Your Jenkins Pipeline succeeded.",
                to: "lawrence.wenboli@gmail.com",
                attachLog: true
            )
        }

        failure {
            emailext(
                subject: "Jenkins Pipeline failed.",
                body: "Your Jenkins Pipeline failed，please check logfile for more details.",
                to: "lawrence.wenboli@gmail.com",
                attachLog: true
            )
        }
    }
    }
}
