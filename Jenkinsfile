node{
   stage('SCM Checkout'){
     git 'https://github.com/rameshkalirawana/maven'
   }
   stage('Compile-Package'){
      // Get maven home path
      def mvnHome =  tool name: 'localMaven', type: 'maven'  
      sh "${mvnHome}/bin/mvn package"
   }  }

