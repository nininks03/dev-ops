pipeline {
    agent any

    tools {
        nodejs 'NodeJS 20'
    }

    stages {
        stage('Clone Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/nininks03/dev-ops'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install'
            }
        }

        stage('Build React App') {
            steps {
                bat 'npm run build'
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
