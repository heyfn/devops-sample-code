
pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'python3 -m venv venv'
                sh 'venv/bin/python -m pip install -r requirements.txt'
                sh 'venv/bin/python -m pip install pytest'
                sh 'venv/bin/python -m pytest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'venv/bin/python -m pip install -r requirements.txt'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Starting application...'
                sh 'venv/bin/python app.py > app.log 2>&1 &'
                sh 'sleep 2'
            }
        }

        stage('Test Application') {
            steps {
                echo 'Testing application...'
                sh 'curl -f http://localhost:5000'
            }
        }
    }
}
