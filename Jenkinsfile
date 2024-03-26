@Library('mylibrary')_
node('built-in')
{
    stage('ContDownload')
    {
        cicd.gitDownload("maven")
    }
    stage('Contbuild')
    {
        cicd.mavenBuild()
    }
    stage('ContDeployment')
    {
        cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraris","172.31.14.111","testapp69")
    }
    stage('ContTesting')
    {
        cicd.gitDownload("FunctionalTesting")
        cicd.runSelenium("ScriptedPipelinewithSharedLibraris")
    }
    stage('contDelivery')
    {
        cicd.tomcatDeploy("ScriptedPipelinewithSharedLibraris","172.31.3.52","prodapp69")
    }
}









