pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }

    stages {
        stage('Run Python Script') {
            steps {
                bat '"C:\\Users\\abdul\\AppData\\Local\\Programs\\Python\\Python313\\python.exe" analyzer.py'
            }
        }

        stage('Archive Report') {
            steps {
                archiveArtifacts artifacts: 'report.txt', fingerprint: true
            }
        }
    }
}
