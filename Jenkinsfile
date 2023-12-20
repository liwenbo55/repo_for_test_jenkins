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
        
        stage('ci'){
            steps{
                sh 'npm cache clean --force'
                sh 'npm -v'
                sh 'node -v'
                sh 'npm install --force'
                sh 'cp .env.example .env'
                sh 'npm run build'
            }
        }

        stage('Deploy to AWS'){
            steps {
                  withAWS(region:'ap-southeast-2',credentials:'lawrence-jenkins-credential') {
                  sh 'echo "Uploading artifacts with AWS creds"'
                    //   s3Upload(pathStyleAccessEnabled: true, payloadSigningEnabled: true, file:'app.py', bucket:'jenkins-s3-bucket-wach')
                      s3Upload(file:'./build', bucket:'p3.techscrum-uat.wenboli.xyz-frontend-uat')
                  }
            }
        }


    }
}
