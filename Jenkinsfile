#!groovy
import groovy.json.JsonSlurperClassic
node {

    def SF_CONSUMER_KEY_SIT='3MVG9rnryk9FxFMUr9jX4zSv9cRduBmdu9_wRKoeQiDA5jY2sBjHu2fcJZoEgNIOhBRxHiQ6tEyV_bYkpp907'
    def SF_USERNAME_SIT='dmahato-sybr@force.com.dmstest'
    def SERVER_KEY_CREDENTIALS_ID='5ea9e40b-16a7-4df3-8caf-7573d80e2482'
    def SF_INSTANCE_URL = 'https://test.salesforce.com'

    

    def toolbelt = tool 'toolbelt'
   
	

      withCredentials([file(credentialsId: SERVER_KEY_CREDENTIALS_ID, variable: 'server_key_file')]) {
	//stages {
	    
        stage('Installation') {
          
         // println ('Inside Installation Stage')
               
		    rc = bat returnStatus: true, script: "\"${toolbelt}\" force:auth:jwt:grant --clientid ${SF_CONSUMER_KEY_SIT} --username ${SF_USERNAME_SIT} --jwtkeyfile \"${server_key_file}\" --setalias SIT --instanceurl ${SF_INSTANCE_URL}"
		    
		    
            bat returnStatus: true, script: "\"${toolbelt}\" force:org:list"

        }
	    
	    

        

//}
}
 
}
