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

