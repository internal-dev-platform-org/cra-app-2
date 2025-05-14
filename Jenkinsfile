pipeline {
    agent {
        docker {
            image 'node:18' // или node:20, если хочешь поновее
            args '-u root --network=host' 
        }
    }

    stages {
        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
                sh 'echo hello world'
            }
        }

        stage('Archive') {
            steps {
                sh 'apt update && apt install -y zip'
                sh 'zip -r build.zip build/'
                archiveArtifacts artifacts: 'build.zip', fingerprint: true
            }
        }
    }
}
