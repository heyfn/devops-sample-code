
pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'python3 -m pip install -r requirements.txt'
                sh 'python3 -m pip install pytest'
                sh 'python3 -m pytest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'python3 -m pip install -r requirements.txt'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Starting application...'
                sh 'python3 app.py &'
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
