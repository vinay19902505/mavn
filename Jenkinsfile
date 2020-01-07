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
                sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/DeclarativePipeline/webapp/target/webapp.war ubuntu@172.31.80.205:/var/lib/tomcat8/webapps/testapp.war'
            }
        }

        stage('continuousTesting')
        {
            steps
            {
			git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
            sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/DeclarativePipeline/testing.jar'
   	    }
        }     
        
    }     
    
}
