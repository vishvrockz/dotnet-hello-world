pipeline {
    agent any

    stages {
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
                // Add deployment logic here
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
