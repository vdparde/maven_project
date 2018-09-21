pipeline {
	agent any 
       
             tools {
                   mvn 'Apache-maven-2.2.1'
                  }
	}
      
          stages {
	   stage ('Pull'){

		    git 'https://github.com/vdparde/maven_project.git'
            	  
			}

	   stage ('Build'){
     		steps {
 			sh 'mvn clean package'
		    }
		
		}

	   stage ('Test'){
		steps {
 		  sh 'mvn test'     
                  }
 		post {
	           always {
			 junit 'target/*.xml'
                      }	
		}
 
	    stage ('Deliver') {
		steps {
		       sh './jenkins/scripts/deliver'
                     }


                }


          }



    }





