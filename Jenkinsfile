#!groovy
import groovy.json.JsonSlurperClassic
node {

    def SF_CONSUMER_KEY_SIT='3MVG9pRzvMkjMb6mdk5cLx15frfwLsrsUVzseijyumrW.AgANObmRo68Ng0nteblTC52JCfV72PDc6BqACpl9'
    
    def SF_USERNAME_SIT='p.prital21@brave-otter-vnbah3.com'
    
    def SERVER_KEY_CREDENTIALS_ID='c0472c34-3399-43ff-8fe0-2fc6819f9577'
    def SF_INSTANCE_URL = 'https://login.salesforce.com'

    

    def toolbelt = tool 'toolbelt'
   
	

      withCredentials([file(credentialsId: SERVER_KEY_CREDENTIALS_ID, variable: 'server_key_file')]) {
	//stages {
	    
        stage('Installation') {
          
         // println ('Inside Installation Stage')
               
		    rc = bat returnStatus: true, script: "\"${toolbelt}\" force:auth:jwt:grant --clientid ${SF_CONSUMER_KEY_SIT} --username ${SF_USERNAME_SIT} --jwtkeyfile \"${server_key_file}\" --setalias Prod --instanceurl ${SF_INSTANCE_URL}"
		    
		    
            bat returnStatus: true, script: "\"${toolbelt}\" force:org:list"

        }
	    
	    

        

//}
}
 
}
