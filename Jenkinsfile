@Library("mysharedlibrary")_

pipeline
{
    agent any
    stages
    {
        stage('Download')
        {
            steps
            {
                script
                {
                    cicd.gitDownload('payments','maven-1')
                }
            }
        }
        stage('Build')
        {
            steps{
                script{
                    cicd.buildArtifact()
                }
            }
        }
    }
}
