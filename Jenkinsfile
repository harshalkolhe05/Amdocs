pipeline {
    agent any
	  
triggers {
        cron('*/5 * * * *')
    }
    
    stages {

        	stage('Wait for user to input text?') {
   		         steps {
        	         	script {
            			        def userInput = input(id: 'userInput', message: 'Merge to?',
            			      parameters: [[$class: 'ChoiceParameterDefinition', defaultValue: 'strDef', 
               			       description:'Update the Title', name:'nameChoice', choices: "Dog\nCat\nElephant\nLion\nTiger"]
             		         	])
           			         println(userInput); 
					data = readFile(file: 'index.html')
                   				println(data)
					data += "<title>"
					println(data)
					def data = userInput 
					println(data)
		      				 data = writeFile(file: 'index.html', text: data)
                   			sh "ls -l"
       				              }	
   			        }
		} }
					post {
					always {
					    echo 'This will always run'
					}
					success {
					    	echo 'This will run only if successful'
						 mail to: 'harshalkolhe05@gmail.com',
				   		 subject: "Job '${JOB_NAME}' (${BUILD_NUMBER}) is waiting for input",
				    		body: "Please go to ${BUILD_URL} and verify the build"
					}
					failure {
					  	mail to: 'harshalkolhe05@gmail.com',
				    		subject: "Job '${JOB_NAME}' (${BUILD_NUMBER}) is waiting for input",
				    		body: "Please go to ${BUILD_URL} and verify the build"
					}
				}
				}
