properties([parameters([choice(choices: ['master', 'dev'], description: 'select branch to build', name: 'branch')])])
node{
   stage('SCM Checkout'){
	echo "Pulling changes from branch ${params.branch}"
     git "https://github.com/rameshkalirawana/maven"
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'localMaven', type: 'maven'  
      sh "${mvnHome}/bin/mvn package"
   }


   stage('Slack Notification'){
	slackSend baseUrl: 'https://hooks.slack.com/services/', 
	channel: 'ttnjrnkings',
	 color: 'Good', 
	message: 'message from jekins', 
	teamDomain: 'rameshttn', 
	tokenCredentialId: 'slack-key'
   }
}
