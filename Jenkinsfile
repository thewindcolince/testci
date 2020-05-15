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
                   
                sh 'echo "creating folder"' 
		sh "ssh ubuntu@ec2-54-244-81-128.us-west-2.compute.amazonaws.com 'mkdir  /var/www/testci'"  	  
                sh 'scp index.html  ubuntu@ec2-54-244-81-128.us-west-2.compute.amazonaws.com:/var/www/testci'
                sh 'echo "restarting apache service"'
                sh "ssh ubuntu@ec2-54-244-81-128.us-west-2.compute.amazonaws.com 'sudo systemctl restart apache2'
       }	 
     }
  }
}
