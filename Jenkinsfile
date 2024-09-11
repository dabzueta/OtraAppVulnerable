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
                    
                    withSonarQubeEnv(credentialsId: 'sonarqubetoken') {
                      
                        sh 'mvn clean package sonar:sonar'
                    }
                   }
                    
                }
            }
           
        }
        
}