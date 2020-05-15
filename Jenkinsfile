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
         
           withCredentials([usernamePassword(credentialsId: 'testci', passwordVariable: 'pass', usernameVariable: 'user')]) {
                               
            		sh 'cd /var/www && mkdir test'
                sh 'cp index.html /var/www/test'
                sh 'sudo systemctl restart apache2'
        }
       }	 
     }
  }
}
