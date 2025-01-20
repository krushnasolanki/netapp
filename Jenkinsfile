
pipeline {
    agent any

    tools {
        // Use the .NET SDK installed on the system
        dotnet 'dotnet'
    }

    stages {
        stage('Restore') {
            steps {
                echo 'Restoring dependencies...'
                sh 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'dotnet build --no-restore'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'dotnet test --no-build'
            }
        }
        stage('Publish') {
            steps {
                echo 'Publishing the application...'
                sh 'dotnet publish -c Release -o ./publish'
            }
        }
    }
}
