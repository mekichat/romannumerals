node {
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git credentialsId: 'd2ecbd81-f94c-41fa-a098-30a13641a293', url: 'git@github.com:mekichat/romannumerals.git'

      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
      
   }
   stage('Build') {
      // Run the maven build
      if (isUnix()) {
         sh "mvn -Dmaven.test.failure.ignore clean package"
      }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
}
