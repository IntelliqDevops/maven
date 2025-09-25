@Library('mylibrary')_


pipeline
{
    agent any
    stages
    {
        stage('Download_Loans')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")
                }
            }
        }
        stage('Build_Loans')
        {
            steps
            {
                script
                {
                    cicd.buildArtifact()
                }
            }
        }
  }
}
