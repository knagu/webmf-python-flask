pipeline {
 

  stages {
   stage('Git Checkout'){
   git url:'https://github.com/knagu/webmf-python-flask.git'
   }
    stage('build') {
      steps {
        sh 'pip install -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python test.py'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }    
    }
  }
}
