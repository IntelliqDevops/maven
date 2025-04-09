@Library('mylibrary')_

pipeline
{
    agent any
    stages
    {
        stage('Download_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("maven")
                }
            }
        }
        stage('Build_Master')
        {
            steps
            {
                script
                {
                    cicd.buildArtifact()
                }
            }
        }
        stage('Deployment_Master')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.15.208","testapp")
                }
            }
        }
        stage('Testing_Master')
        {
            steps
            {
                script
                {
                    cicd.gitDownload("FunctionalTesting")
                    cicd.runSelenium("DeclarativePipelinewithSharedLibraries")
                }
            }
        }
        stage('Delivery_Master')
        {
            steps
            {
                script
                {
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.13.103","prodapp")
                }
            }
        }
        
        
        
        
        
    }
}
