node 
  { 
	  stage ('workspace clean') {
	  cleanWs()	  
	  }
	  stage('GitSCM')
	  {
		  git url: 'https://github.com/knagu/webmf-python-flask.git'
	  }	  
   stage('Build Stage')
	  {
		sh 'pip install -r requirements.txt'
		echo "Build Successful"
	  }
   stage('Test') {
	  sh 'python test.py'
	  echo "Tests successful"
	  }
	  stage('SonarQube analysis') {
 	 // requires SonarQube Scanner 2.8+
  	def scannerHome = tool 'SonarScanner';
 	 withSonarQubeEnv('sonar') {
    	sh "${scannerHome}/bin/sonar-scanner"
  }
}
   
  }
