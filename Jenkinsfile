pipeline{
    agent any 
    
    stages {
        withCredentials([string(credentialsId: 'Jenkins-GithubApp', variable: 'GITHUB_TOKEN')]) {
            stage('Git Private Checkout')
        }
        stage('Git Private Checkout'){
            steps{
                script{
                    git branch: 'main', url: 'https://github.com/dabzueta/VulnerableApp.git'
                }
            }
        }
        stage('Static code analysis'){
            steps{
                script{
                    scannerHome = tool 'sonar-scanner'
                }
                   
                withSonarQubeEnv('sonarserver') { 
                    sh "${scannerHome}/bin/sonar-scanner"
                }
            }
        }
    }
}
