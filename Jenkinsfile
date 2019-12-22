pipeline
{
    agent any
    stages
    {
        stage('ContinousDownload:Master')
        {
            steps
            {
                git 'https://github.com/tripathiravi07/Jenkins-MultiBranchPipeline.git'
            }
        }
        stage('ContinousBuild:Master')
        {
            steps
            {
                sh label: '', script: 'mvn package'
            }
        }
        stage('ContinousDeployment:Master')
        {
            steps
            {
                sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/MultiBranch_Pipeline_master/target/my-app.war ubuntu@172.31.35.155:/var/lib/tomcat8/webapps/testapp.war'
            }
        }
        stage('ContinousDelivery:Master')
        {
            steps
            {
                sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/MultiBranch_Pipeline_master/target/my-app.war ubuntu@172.31.26.147:/var/lib/tomcat8/webapps/prodapp.war'
            }
        }
    }
}

