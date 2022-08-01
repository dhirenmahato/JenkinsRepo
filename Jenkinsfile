#!groovy
import groovy.json.JsonSlurperClassic
node {

    def SF_CONSUMER_KEY_SIT='3MVG95mg0lk4batjNdzwuD_VoHRyM7w.DoW_csdbJOEccKaUvNUBq8c17TEuvlbNKhG1DgWSXxNy2jABzPOwc'
    def SF_CONSUMER_KEY_PROD='3MVG9pRzvMkjMb6mdk5cLx15frfwLsrsUVzseijyumrW.AgANObmRo68Ng0nteblTC52JCfV72PDc6BqACpl9'
    def SF_USERNAME_SIT='dhiren@deloitte.com'
    def SF_USERNAME_PROD='p.prital21@brave-otter-vnbah3.com'
    def SERVER_KEY_CREDENTIALS_ID='5ea9e40b-16a7-4df3-8caf-7573d80e2482'
    def SF_INSTANCE_URL = 'https://login.salesforce.com'

    

    def toolbelt = tool 'toolbelt'
   
	

      withCredentials([file(credentialsId: SERVER_KEY_CREDENTIALS_ID, variable: 'server_key_file')]) {
	//stages {
	    
        stage('Installation') {
          
         // println ('Inside Installation Stage')
               
		    rc = bat returnStatus: true, script: "\"${toolbelt}\" force:auth:jwt:grant --clientid ${SF_CONSUMER_KEY_SIT} --username ${SF_USERNAME_SIT} --jwtkeyfile \"${server_key_file}\" --setalias DMTest --instanceurl ${SF_INSTANCE_URL}"
		    rc = bat returnStatus: true, script: "\"${toolbelt}\" force:auth:jwt:grant --clientid ${SF_CONSUMER_KEY_PROD} --username ${SF_USERNAME_PROD} --jwtkeyfile \"${server_key_file}\" --setalias DMProd --instanceurl ${SF_INSTANCE_URL}"
		    
            bat returnStatus: true, script: "\"${toolbelt}\" force:org:list"

        }
	    
	    

        

//}
}
 
}
