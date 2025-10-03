pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/vishvrockz/dotnet-hello-world.git'
            }
        }

        stage('Build') {
            steps {
                bat 'dotnet build'
            }
        }

        stage('Test') {
            steps {
                bat 'dotnet test'
            }
        }

        stage('Publish') {
            steps {
                bat 'dotnet publish -c Release -o out'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application'
                // Deployment logic here (e.g., copy files, restart services, etc.)
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
