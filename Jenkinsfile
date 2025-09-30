pipeline {
    agent any

    tools {
        nodejs "NodeJS"
    }

    stages {
        stage('Clone') {
            steps {
                git 'https://github.com/Sameera008/Trading-UI.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run Tests') {
    steps {
        script {
            def result = sh(script: 'npm test', returnStatus: true)
            if (result != 0) {
                echo "Tests failed, but continuing pipeline."
            }
        }
    }
}

        stage('Build') {
            steps {
                echo 'Build step (if needed)'
            }
        }
    }
}
