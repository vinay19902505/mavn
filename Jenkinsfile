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

	 stage('continuousDeploy')
	 {
	 steps
	 }
    sh label: '', script: 'scp /home/ubuntu/.jenkins/workspace/Pipeline/webapp/target/webapp.war ubuntu@172.31.80.205:/var/lib/tomcat8/webapps/testapp.war'

}
}
        
       
    }
    
      
    
}
