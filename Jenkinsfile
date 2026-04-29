pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')   // auto check every minute
    }

    stages {
        stage('Clone Repository') {
            steps {
               git 'https://github.com/raashid721/log-analyzer-pipeline.git'
            }
        }

        stage('Run Python Script') {
            steps {
                sh 'python3 analyzer.py'
            }
        }

        stage('Archive Report') {
            steps {
                archiveArtifacts artifacts: 'report.txt', fingerprint: true
            }
        }
    }
}
