
pipeline
{
    agent any
    stages
    {
        stage('ContinousDownload:Loans')
        {
            steps
            {
                git 'https://github.com/tripathiravi07/Jenkins-MultiBranchPipeline.git'
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
                sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/MultiBranch_Pipeline_loans/target/my-app.war ubuntu@172.31.35.155:/var/lib/tomcat8/webapps/testingapp.war'
            }
        }
    }
}

