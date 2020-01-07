pipeline
{
agent any
{
stages
{
    stage('continousdownload') {
    
	Steps{
	 git 'https://github.com/vinay19902505/mavn.git'
	}
}
 stage('continousBuild') {
    
	Steps{
	 sh label: '', script: 'mvn package'
	}
}
}
}
}
