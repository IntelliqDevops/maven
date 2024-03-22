@Library('mylibrary')_

node('built-in')
{
    stage('ContDownload')
    {
        cicd.gitDownload("maven")
    }
    stage('ContBuild')
    {
         cicd.mavenBuild()

    }
    stage('ContDeployment')
    {
        cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraries","172.31.20.244","testapp")

    }
    stage('ContTesting')
    {
        
       cicd.gitDownload("FunctionalTesting")
        cicd.runSelenium("ScriptedPipelinewithSharedLibraries")

    }  
    stage('ContDelivery')
    {
        cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraries","172.31.30.157","prodapp")
    }
    
    
}
