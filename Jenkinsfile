pipeline {
    agent any

    stages {
        stage('Clean') {
          cleanWs()
        }

        stage('Checkout') {
            steps {
                git 'https://github.com/instant-build/instant.build-angular.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Build') {
            steps {
                sh 'ng build'
            }
        }

        stage('Deploy') {
            steps {
                sh 'cp -r dist/* /var/www/'
            }
        }
    }
}
