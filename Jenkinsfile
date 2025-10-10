pipeline {
    agent any 
    stages {
        stage('download') {
            steps{
                git 'https://github.com/purnachandraredddy/maven-1.git'
            }
        }
        stage('build'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp /home/ubuntu/.jenkins/workspace/Development1/webapp/target/webapp.war ubuntu@172.31.24.219:/var/lib/tomcat9/webapps/testapp.war'
            }
        }
        stage('test'){
            steps{
                git 'git@github.com:purnachandraredddy/Testing.git'
                sh 'java -jar /home/ubuntu/.jenkins/workspace/Development1/testing.jar'
            }
        }
        
    }
}
