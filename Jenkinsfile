pipeline {
    agent any

    stages {

        	stage('Wait for user to input text?') {
   		         steps {
        	         	script {
            			        def userInput = input(id: 'userInput', message: 'Merge to?',
            			      parameters: [[$class: 'ChoiceParameterDefinition', defaultValue: 'strDef', 
               			       description:'describing choices', name:'nameChoice', choices: "Harshal\nAmdocs"]
             		         	])

           			         println(userInput); 
				
       				              }		
   			             }

	                                           }
	    
           }
			 post {
			always {
			    echo 'This will always run'
			}
			success {
			    echo 'This will run only if successful'
			}
			failure {
			    mail to: "harshalkolhe05@gmail.com";
			}

  		  }
  }
