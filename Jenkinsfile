pipeline
{
    agent any
    stages
    {
	
	
	
	
        stage('ContDownload')
        {
            steps
            {
			    script
				{
				try 
				{
                git 'https://github.com/vinay19902505/mavn.git'
				}
				catch(Exception e1)
				{
				mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'download failed', to: 'hilton.ciber@gmail.com'

				}
				}
            }
        }
        stage('ContBuild')
        {
            steps
            {
			script
				{
				try 
				  {
                  sh 'mvn package'
				  }
				catch(Exception e1)
				  {
				mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'build failed', to: 'hilton.ciber@gmail.com'

				  }
				}
                
            }
        }
        stage('ContDeployment')
        {
            steps
            {
			script
				{
				try 
				  {
                 sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/DeclarativePipeline/webapp/target/webapp.war ubuntu@172.31.80.205:/var/lib/tomcat8/webapps/testapp.war'
				  }
				catch(Exception e1)
				  {
				mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'deploy failed', to: 'hilton.ciber@gmail.com'

				  }
				}
			
			
			
			
                
            }
        }

        stage('continuousTesting')
        {
            steps
            {
			
			script
				{
				try 
				  {
                 git 'https://github.com/selenium-saikrishna/FunctionalTesting.git'
            sh label: '', script: 'java -jar /home/ubuntu/.jenkins/workspace/DeclarativePipeline/testing.jar'
				  }
				catch(Exception e1)
				  {
				mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'test failed', to: 'hilton.ciber@gmail.com'

				  }
				}
			
			
			
			
			
   	        }
        }     
    } 

    post
	{
			success
			{
			
			   sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/DeclarativePipeline/webapp/target/webapp.war ubuntu@172.31.90.97:/var/lib/tomcat8/webapps/prodapp.war'
	
			}
			failure
			{
			mail bcc: '', body: '', cc: '', from: '', replyTo: '', subject: 'delivery failed', to: 'hilton.ciber@gmail.com'
			}
	
	}
    
}




