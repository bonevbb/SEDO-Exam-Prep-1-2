pipeline {
    agent any

    stages {
        stage('Build and Test') {
            when {
                anyOf {
                    branch 'main'
                    branch 'feature'
                }
            }
            stages {
                stage('Restore') {
                    steps {
                        sh 'dotnet restore'
                    }
                }

                stage('Build') {
                    steps {
                        sh 'dotnet build --no-restore'
                    }
                }

                stage('Test') {
                    steps {
                        sh 'dotnet test --no-build --verbosity normal'
                    }
                }
            }
        }
    }
}
