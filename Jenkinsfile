node{
	stage('checkout code'){	
	       checkout	scm	
	}
	
	stage ('Build'){
		sh "mvn clean install -Dmaven.test.skip=true"
	}
	
	//stage('Compile-Package'){
	    //def mvnHome = tool name: 'maven3', type: 'maven'
		//sh "${mvnHome}/bin/mvn package"
		//sh 'mvn package'
	//}

	stage ('Notification'){
		//slackSend color: 'good', message: 'Deployment Sucessful'
		emailext (
		      subject: "Job Completed",
		      body: "Jenkins Pipeline Job for Maven Build got completed !!!",
		      to: "sikandarali@ieee.org"
		    )
	}
}	
