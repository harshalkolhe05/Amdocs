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
            mail bcc: '', body: "<b>Example</b><br><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "ERROR CI: Project name -> ${env.JOB_NAME}", to: "harshalkolhe05@gmail.com";
        
        }
       
    }
  }
