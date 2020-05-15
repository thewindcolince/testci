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
                   
                sh 'echo "creating folder"'      
            		sh 'cd /var/www && mkdir test'
                sh 'echo "copying file in folder"'
                sh 'cp index.html /var/www/test'
                sh 'echo "restart apache service"'
                sh 'sudo systemctl restart apache2'
        }
       }	 
     }
  }
}
