@Library('samplelibrary')_

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
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.18.248","testapp")
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
                    cicd.deployTomcat("DeclarativePipelinewithSharedLibraries","172.31.19.128","prodapp")
                }
            }
        }
    }
}
