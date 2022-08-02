pipeline {
    agent any
    
    environment {

    def SF_CONSUMER_KEY='3MVG95mg0lk4batjNdzwuD_VoHRyM7w.DoW_csdbJOEccKaUvNUBq8c17TEuvlbNKhG1DgWSXxNy2jABzPOwc'
    def SF_USERNAME='dhiren@deloitte.com'
    def SERVER_KEY_CREDENTIALS_ID='5ea9e40b-16a7-4df3-8caf-7573d80e2482'
    def SF_INSTANCE_URL = 'https://login.salesforce.com'

    

    def toolbelt = tool 'toolbelt'
    } 
	  stages {
	    stage('SYSTEM INTEGRATION TESTING') {
		 
      steps {
				println('Inside Production Deployments')
		     bat returnStatus: true, script: "\"${toolbelt}\" force:org:list"
		    bat returnStatus: true, script: "\"${toolbelt}\" force:mdapi:retrieve -r \"metadata\" -u Test -k \"manifest\\package.xml\""
                    bat returnStatus: true, script: "\"${toolbelt}\" force:mdapi:deploy -f \"metadata/unpackaged.zip\" -u Prod -w 10 "
      }
      }
    }
  }