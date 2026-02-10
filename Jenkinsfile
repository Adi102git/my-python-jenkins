pipeline {
    agent {
        docker {
            image 'python:3.12-slim'
            args '--rm'
        }
    }

    stages {
        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip install --upgrade pip'
                sh 'if [ -f requirements.txt ]; then pip install -r requirements.txt; fi'
            }
        }

        stage('Run Python Script') {
            steps {
                sh 'python mytest.py'
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished. Docker container removed automatically.'
        }
    }
}

