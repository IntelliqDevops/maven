@Library('mylibrary')_

node('built-in')
{
    stage('ContDownload_Loans')
    {
        cicd.gitDownload("maven")
    }
    stage('ContBuild_Loans')
    {
         cicd.mavenBuild()

    }
    
    
}
