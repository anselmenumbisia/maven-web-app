// Powered by Infostretch 

timestamps {

node () {

	stage ('BOA-project - Checkout') {
 	 checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: 'sourcecode', url: 'https://github.com/anselmenumbisia/maven-web-app.git']]]) 
	}
	stage ('BOA-project - Build') {
 	
// Unable to convert a build step referring to "hudson.plugins.timestamper.TimestamperBuildWrapper". Please verify and convert manually if required.		// Maven build step
	withMaven(maven: 'maven3.8.1') { 
 			if(isUnix()) {
 				sh "mvn clean package " 
			} else { 
 				bat "mvn clean package " 
			} 
 		}		// Maven build step
	withMaven(maven: 'maven3.8.1') { 
 			if(isUnix()) {
 				sh "mvn sonar:sonar " 
			} else { 
 				bat "mvn sonar:sonar " 
			} 
 		}		// Maven build step
	withMaven(maven: 'maven3.8.1') { 
 			if(isUnix()) {
 				sh "mvn deploy " 
			} else { 
 				bat "mvn deploy " 
			} 
 		} 
	}
}
}