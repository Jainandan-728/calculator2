pipeline {
    agent any

    stages {

        stage('Setup Python Environment') {
            steps {
                sh '''
                python3 -m venv venv
                ./venv/bin/pip install --upgrade pip
                '''
            }
        }

        stage('Install Dependencies') {
            steps {
                sh '''
                ./venv/bin/pip install -r requirements.txt
                '''
            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                ./venv/bin/python -m unittest test_calculator.py
                '''
            }
        }

    }

    post {
        success {
            echo 'Build and Tests Passed Successfully'
        }
        failure {
            echo 'Build Failed'
        }
    }
}
