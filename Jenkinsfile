
pipeline
{
    agent any
    stages
    {
        stage('ContinousDownload:Loans')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven'
            }
        }
        stage('ContinousBuild:Loans')
        {
            steps
            {
                sh label: '', script: 'mvn package'
            }
        }
        stage('ContinousDeployment:Loans')
        {
            steps
            {
                sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/DeclarativePipeline/webapp/target/webapp.war ubuntu@172.31.35.155:/var/lib/tomcat8/webapps/testingapp.war'
            }
        }
    }
}

