#!groovy


//  node{
//   def mvnHome
  
//   stage('Preparation') { // for display purposes
      // Get some code from a GitHub repository
 //     https://github.com/chandrayarramreddy/PilotProject.git
      // Get the Maven tool.
      // ** NOTE: This 'M3' Maven tool must be configured
      // **       in the global configuration.           
 //     mvnHome = tool 'M2_HOME'
     //    mvnHome = tool 'Maven'
 //  }
 //  stage('Build') {
      // Run the maven build
  //    if (isUnix()) {
  //       sh "'${mvnHome}/bin/mvn' clean package"
   //   } else {
  //       bat(/"${mvnHome}\bin\mvn" clean package/)
   //   }
  // }
  
// }  



node {
  // Need to replace the '%2F' used by Jenkins to deal with / in the path (e.g. story/...)
  // because tests that do getResource will escape the % again, and the test files can't be found.
  // See https://issues.jenkins-ci.org/browse/JENKINS-34564 for more.
 // ws("workspace/${env.JOB_NAME}/${env.BRANCH_NAME}".replace('%2F', '_')) {
    // Mark the code checkout 'stage'....
    stage 'Checkout'
    checkout scm

    // Mark the code build 'stage'....
    stage 'Build'

  //  def mvnHome = tool 'maven-3.3.9'
    def  mvnHome = tool 'M2_HOME'
 //   sh "${mvnHome}/bin/mvn clean package"
 
   bat(/"${mvnHome}\bin\mvn" clean package/)
    
  //  junit testResults: '**/surefire-reports/*.xml'
//  }
}
