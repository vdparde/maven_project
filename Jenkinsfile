pipeline {
	agent{ 
             label "jenkins_slave"
            }
            tools {

                   maven 'Apache-Maven-2.2.1'

                  }
	stages {
	   stage ('Pull'){

 		git url: 'https://github.com/vdparde/maven_project.git'              
             	  }

	   stage ('Build'){
			echo "Building....."
     		steps {

 			sh 'mvn clean package'
		    }
		
		}

	   stage ('Test'){
			echo "Testing......"
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




}
