node {
   def mvnHome
   stage('clone') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/Prakashja/mvn-jfrog-setup.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
   }

   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archiveArtifacts 'target/*.jar'
   }
}
