@Library('mylibrary')_
node('built-in')
{
    stage('ContDownload_Master')
    {
        cicd.gitDownload("maven")
    }
    stage('Contbuild_Master')
    {
        cicd.mavenBuild()
    }
    stage('ContDeployment_Master')
    {
        cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraris","172.31.14.111","testapp69")
    }
    stage('ContTesting_Master')
    {
        cicd.gitDownload("FunctionalTesting")
        cicd.runSelenium("ScriptedPipelinewithSharedLibraris")
    }
    stage('contDelivery_Master')
    {
        cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraris","172.31.3.52","prodapp69")
    }
}









