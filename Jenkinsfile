node {
   def M2_HOME
   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
      git 'https://github.com/jglick/simple-maven-project-with-tests.git'
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
      M2_HOME = tool 'M2'
   }
   stage('Build') {
      // Run the maven build
      if (isUnix()) {
         sh "'${M2_HOME}/bin/mvn' -Dmaven.test.failure.ignore clean package"
      } else {
         bat(/"${M2_HOME}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
