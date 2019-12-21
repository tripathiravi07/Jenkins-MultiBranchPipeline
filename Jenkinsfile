pipeline
{
    agent any
    stages
    {
        stage('ContinousDownload:master')
        {
            steps
            {
                git 'https://github.com/tripathiravi07/Jenkins-MultiBranchPipeline.git'
            }
        }
        stage('ContinousBuild:master')
        {
            steps
            {
                sh label: '', script: 'mvn package'
            }
        }
        stage('ContinousDeployment:master')
        {
            steps
            {
                sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/MultiBranch_Pipeline_master/target/my-app.war ubuntu@172.31.35.155:/var/lib/tomcat8/webapps/testapp.war'
            }
        }
        stage('ContinousDelivery:master')
        {
            steps
            {
                sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/MultiBranch_Pipeline_master/target/my-app.war ubuntu@172.31.26.147:/var/lib/tomcat8/webapps/prodapp.war'
            }
        }
    }
}

