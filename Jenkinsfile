pipeline {
    agent any

    stages {

        stage('Dotnet restore') {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                bat "dotnet restore"
            }
        }

        stage('Dotnet build') {
            when {
                anyOf
                 {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                bat "dotnet build --no-restore"
            }
        }

        stage('Run the tests') {
            when {
                anyOf
                 {
                    branch 'main'
                    branch 'feature'
                }
            }
            steps {
                bat "dotnet test --no-build --verbosity normal"
            }
        }
    }
}

