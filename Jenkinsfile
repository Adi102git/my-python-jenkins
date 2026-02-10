pipeline {
    agent {
        docker {
            image 'python:Python 3.12.3'
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

