pipeline
{
    agent any
    stages
    {
        stage('continuousDownload')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven.git'
            }
        }
        stage('continuousBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('ContinuousDeployment')
        {
            steps
            {
                deploy adapters: [tomcat9(credentialsId: '45696a2b-30a0-4e1d-8a66-17d945f34737', path: '', url: 'http://172.31.14.111:8080')], contextPath: 'testapp', war: '**/*.war'
            }
        }
        stage('ContinuousTesting')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/FunctionalTesting.git'
                sh 'java -jar /var/lib/jenkins/workspace/DeclrativePipeline1/testing.jar'
            }
        }
        stage('ContinuousDelivery')
        {
            steps
            {
                input message: 'Need approval from DM!', submitter: 'sumit'
                deploy adapters: [tomcat9(credentialsId: '45696a2b-30a0-4e1d-8a66-17d945f34737', path: '', url: 'http://172.31.3.52:8080')], contextPath: 'myprodapp', war: '**/*.war'
            }
        }
    }
}
