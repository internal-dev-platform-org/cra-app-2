pipeline {
    agent any

    stages {
        stage('Install') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'npm run build'
            }
        }

        stage('Archive') {
            steps {
                sh 'zip -r build.zip build/'
                archiveArtifacts artifacts: 'build.zip', fingerprint: true
            }
        }
    }
}
