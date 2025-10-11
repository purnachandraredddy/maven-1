pipeline{
    agent any 
    stages {
        stage('Download'){
            steps{
                git branch: 'main', url: 'https://github.com/purnachandraredddy/maven-1.git'
            }
        }
        stage('Build'){
            steps{
                 sh '/opt/homebrew/bin/mvn package'
            }
        }
        stage('deploy'){
            steps{
                sh 'scp /Users/purnachandrareddypeddasura/.jenkins/workspace/ScriptedPipeline/webapp/target/webapp.war purna@192.168.64.7:/tmp/testapp.war'
                sh 'ssh purna@192.168.64.7 "sudo mv /tmp/testapp.war /var/lib/tomcat10/webapps/testapp.war && sudo chown tomcat:tomcat /var/lib/tomcat10/webapps/testapp.war"'
            }
        }
        stage('test'){
            steps{
                    git branch: 'master', url: 'https://github.com/purnachandraredddy/Testing.git'
                    sh 'java -jar /Users/purnachandrareddypeddasura/.jenkins/workspace/ScriptedPipeline/testing.jar'
            }
        }
    }
}
