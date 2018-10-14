properties([parameters([choice(choices: ['master', 'dev',], description: 'select branch', name: 'branch')]), pipelineTriggers([githubPush()])])
node{
   stage('SCM Checkout'){
	echo "Pulling changes from branch ${params.branch}"
     git 'https://github.com/rameshkalirawana/maven', branch: "${params.branch}"
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'localMaven', type: 'maven'  
      sh "${mvnHome}/bin/mvn package"
   }

   stage('Email Notification'){
      mail bcc: '', body: '''jenkins email alerts
      Thanks
      Hari''', cc: '', from: '', replyTo: '', subject: 'Jenkins Job', to: 'rameshchand@tothenew.com'
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
