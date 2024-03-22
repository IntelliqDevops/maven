@Library('mylibrary')_

node('built-in')
{
    stage('ContDownload_Master')
    {
        cicd.gitDownload("maven")
    }
    stage('ContBuild_Master')
    {
         cicd.mavenBuild()

    }
    stage('ContDeployment_Master')
    {
        cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraries","172.31.20.244","testapp")

    }
    stage('ContTesting_Master')
    {
        
       cicd.gitDownload("FunctionalTesting")
        cicd.runSelenium("ScriptedPipelinewithSharedLibraries")

    }  
    stage('ContDelivery_Master')
    {
        cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraries","172.31.30.157","prodapp")
    }
    
    
}
