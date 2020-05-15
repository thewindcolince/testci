pipeline {
  agent any
  stages {
    stage('build') {
      agent any
      steps {
        sh 'echo "Hello colince"'
      }
    }

     stage('deploy to ecs') {
         agent any
       	 steps {
           #withCredentials([usernamePassword(credentialsId: 'hello-kb', passwordVariable: 'pass', usernameVariable: 'user')]) {

        	 withCredentials(credentialsId:'testci') {
            		sh 'cd /var/www && mkdir test'
                sh 'cp index.html /var/www/test'
                sh 'sudo systemctl restart apache2'
            
        	  }
              }	 
       	 }
  }
}
