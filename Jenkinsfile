pipeline {
    agent any

    tools {
        git 'Git'  // Ensure Git is configured in Global Tool Configuration
        dotnet 'dotnet-sdk'  // Specify the .NET SDK if configured
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/vishvrockz/dotnet-hello-world.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    bat 'dotnet build'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    bat 'dotnet test'
                }
            }
        }

        stage('Publish') {
            steps {
                script {
                    bat 'dotnet publish -c Release -o out'
                }
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying the application'
                // Add any deployment logic here (e.g., copy to IIS, AWS, etc.)
            }
        }
    }

    post {
        always {
            cleanWs()
        }
    }
}
