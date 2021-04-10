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
					 if (currentBuild.currentResult == 'FAILURE') {
      				step([$class: 'Mailer', notifyEveryUnstableBuild: true, recipients: "harshalkolhe05@gmail.com, sendToIndividuals: true])
    					}
       				              }		
   			             }

	                                           }
	    
           }
  }
