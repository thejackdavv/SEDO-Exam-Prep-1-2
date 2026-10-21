pipeline{
    agent any
    stages{
        stage("restore"){
            when {
                anyOf {
                    branch "main"
                    branch "feature"
                }
            }
            steps{
                sh "dotnet restore"
            }
        }
        stage("build"){
            when {
                anyOf {
                    branch "main"
                    branch "feature"
                }
            }
            steps{
                sh "dotnet build --no-restore"
            }
        }
        stage("test"){
            when {
                anyOf {
                    branch "main"
                    branch "feature"
                }
            }
            steps{
                sh "dotnet test --no-build --verbosity normal"
            }
        }
    }
    
}