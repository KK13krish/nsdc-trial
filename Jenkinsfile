pipeline {
    agent any

    tools {
        nodejs 'NodeJS-18'
    }

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/KK13krish/nsdc-trial.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                dir('welcome-react') {
                    bat 'npm install'
                }
            }
        }

        stage('Build React App') {
            steps {
                dir('welcome-react') {
                    bat 'npm run build'
                }
            }
        }
    }

    post {
        success {
            echo 'React build successful 🎉'
        }
        failure {
            echo 'Build failed ❌'
        }
    }
}
