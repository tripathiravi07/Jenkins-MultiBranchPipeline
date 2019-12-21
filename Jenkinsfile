pipeline
{
    agent any
    stages
    {
        stage('ContinousDownload')
        {
            steps
            {
                git 'https://github.com/intelliqittrainings/maven'
            }
        }
        stage('ContinousBuild')
        {
            steps
            {
                sh label: '', script: 'mvn package'
            }
        }
        stage('ContinousDeployment')
        {
            steps
            {
                sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/DeclarativePipeline/webapp/target/webapp.war ubuntu@172.31.35.155:/var/lib/tomcat8/webapps/testingapp.war'
            }
        }
        stage('ContinousDelivery')
        {
            steps
            {
                sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/DeclarativePipeline/webapp/target/webapp.war ubuntu@172.31.26.147:/var/lib/tomcat8/webapps/prodapp.war'
            }
        }
    }
}

