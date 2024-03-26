@Library('mylibrary')_
node('built-in')
{
    stage('ContDownload_Loans')
    {
        cicd.gitDownload("maven")
    }
    stage('Contbuild_Loans')
    {
        cicd.mavenBuild()
    }
}









