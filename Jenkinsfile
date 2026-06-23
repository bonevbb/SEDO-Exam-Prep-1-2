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
                        sh '/usr/local/bin/dotnet restore'
                    }
                }

                stage('Build') {
                    steps {
                        sh '/usr/local/bin/dotnet build --no-restore'
                    }
                }

                stage('Test') {
                    steps {
                        sh '/usr/local/bin/dotnet test --no-build --verbosity normal'
                    }
                }
            }
        }
    }
}
