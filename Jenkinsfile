pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Cloning repository...'
                git branch: 'main', url: 'https://github.com/Ria-Thadani/MERN-Ecommerce-Site.git'
            }
        }

        stage('Install Backend Dependencies') {
            steps {
                dir('backend') {
                    bat 'echo MONGO_URL=mongodb://127.0.0.1:27017/ecommerce > .env'
                    bat 'echo SECRET_KEY=secret-key >> .env'
                    bat 'npm install'
                }
            }
        }

        stage('Install Frontend Dependencies') {
            steps {
                dir('frontend') {
                    bat 'npm install'
                }
            }
        }

        stage('Build Completed') {
            steps {
                echo 'Build Successful!'
            }
        }
    }
}