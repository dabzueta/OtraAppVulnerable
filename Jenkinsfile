pipeline{
    agent any 
    stages {
        stage('Git Checkout'){
            steps{
                script{
                    git branch: 'main', url: 'https://github.com/dabzueta/OtraAppVulnerable.git'
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
