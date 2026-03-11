pipeline {
    agent any

    stages {

        stage('Clone Repo') {
            steps {
                git branch: 'main',
                url: 'https://github.com/Jainandan-728/calculator2.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python3 -m unittest test_calculator.py'
            }
        }

    }
}
