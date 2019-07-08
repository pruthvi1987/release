pipeline{
    
    agent any
    stages{
        stage('Build'){
            steps{
                
                
                bat "C:\\Users\\pruthviraj.s.surve\\apache-maven-3.6.1\\bin\\mvn -B -DskipTests clean package"
                
            }
        }
        stage('Test'){
            steps{
                bat "C:\\Users\\pruthviraj.s.surve\\apache-maven-3.6.1\\bin\\mvn test"
            }
            post{
                always{
                    junit '**/target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deploy'){
            steps{
                bat "C:\\Users\\pruthviraj.s.surve\\apache-maven-3.6.1\\bin\\mvn package"
            }
        }
    }
}