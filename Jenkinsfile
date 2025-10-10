pipeline {
    agent any 
    stages {
        stage('download') {
            steps{
                git branch: 'main', url: 'https://github.com/purnachandraredddy/maven-1.git'
            }
        }
        stage('build'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy') {
            steps {
                sh 'scp /home/ubuntu/.jenkins/workspace/Development/webapp/target/webapp.war ubuntu@172.31.16.199:/var/lib/tomcat10/webapps/testapp.war'
            }
        }
        stage('test'){
            steps{
                git branch: 'main', url: 'https://github.com/purnachandraredddy/Testing.git'
                sh 'java -jar /home/ubuntu/.jenkins/workspace/Development/testing.jar'
            }
        }
        stage('delievery'){
            steps{
                 sh 'scp /home/ubuntu/.jenkins/workspace/Development/webapp/target/webapp.war ubuntu@172.31.29.123:/var/lib/tomcat10/webapps/prodapp.war'

            }
        }
    }
}
