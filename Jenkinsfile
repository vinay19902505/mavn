pipeline
{
    agent any
    stages
    {
	
	
	
	
        stage('ContDownload')
        {
            steps
            {
                git 'https://github.com/vinay19902505/mavn.git'
            }
        }
        stage('ContBuild')
        {
            steps
            {
                sh 'mvn package'
            }
        }
        stage('ContDeployment')
        {
            steps
            {
                sh 'scp /var/lib/jenkins/workspace/Declarative_Pipeline/webapp/target/webapp.war vagrant@10.10.10.32:/var/lib/tomcat7/webapps/qaenv.war'
            }
        }
        
    }     
    
}
