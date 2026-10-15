pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'pip install -r requirements.txt'
                sh 'pip install pytest'
                sh 'pytest test_app.py'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Application') {
            steps {
                echo 'Starting application...'
                sh 'python app.py &'
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
