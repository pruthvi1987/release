pipeline{
    
    agent any
    stages{
        stage('Build'){
            steps{
                bat "rmdir /s /q my-app"
                bat "git clone https://github.com/pknowledge/my-app.git"
                bat "C:\\Users\\pruthviraj.s.surve\\apache-maven-3.6.1\\bin\\mvn clean -f my-app"
                
            }
        }
        stage('Test'){
            steps{
                bat "C:\\Users\\pruthviraj.s.surve\\apache-maven-3.6.1\\bin\\mvn test -f my-app"
            }
            post{
                always{
                    junit 'my-app/target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deploy'){
            steps{
                bat "C:\\Users\\pruthviraj.s.surve\\apache-maven-3.6.1\\bin\\mvn package -f my-app"
            }
        }
    }
}