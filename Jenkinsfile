pipeline {
    agent any
    parameters {
        choice(
           name: 'Action',
           choices: "Deploy\nDestroy",
           description: 'For Tetsing' )
     }	
	stages {
	    stage ('Build and Deployment') {
	        steps {
                   script {
	              if ("$params.Action" == "Deploy" ) {
                         sh '''
                            sudo docker-compose up --build -d
                         '''
			 echo 'stage is successfully deployed'
		      } else { 
			 sh '''
                            sudo docker-compose down --rm all
                         '''      
			 echo 'stage is successfully destroyed'
		      }	      
                   }
               }
            }  
	}
}
