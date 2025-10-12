pipeline{
    agent any 
    stages {
        stage('Download_loans'){
            steps{
                git branch: 'main', url: 'https://github.com/purnachandraredddy/maven-1.git'
            }
        }
        stage('Build_loans'){
            steps{
                 sh '/opt/homebrew/bin/mvn package'
            }
        }
    }
}
