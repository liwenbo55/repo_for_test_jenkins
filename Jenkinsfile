// Jenkinsfile by Lawrence
pipeline {
    agent any

    stages {
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
