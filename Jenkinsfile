pipeline {
    agent any

//     environment {
//         PATH = "${tool 'NodeJS'}/bin😒{tool 'AngularCLI'}/bin😒{env.PATH}"
//     }

    stages {
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
                sh 'ng build --prod'
            }
        }

        stage('Deploy') {
            steps {
                sh 'cp -r dist/* /var/www/'
            }
        }
    }
}
