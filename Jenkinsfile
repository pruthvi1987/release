pipeline{
    
    agent any
    stages{
        stage('Build'){
            steps{
                
                
                bat "mvn -B -DskipTests clean"
                bat "mvn install" 
                
            }
        }
        stage('Test'){
            steps{
                bat "mvn test"
            }
            post{
                success{
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deploy'){
            steps{
                bat "mvn package"
            }
        }
    }
}