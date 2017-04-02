#!groovy
//def buildstep = fileLoader.fromGit('buildSteps', gitURL, env.BRANCH_NAME,'', '')
def currentBranch(branchName) {
    return env.BRANCH_NAME == branchName
    }
node {

if (currentBranch('dev')) {
   stage ('Checkout') {
   checkout scm
   }
    // Mark the code build 'stage'....
   // stage 'Build'

    // def mvnHome = tool 'maven-3.3.9'
  stage('Build') {  //Build steps go here
    sh "/DevOps/maven/apache-maven-3.3.9/bin/mvn clean install"
    } 
// stage('NUnit Tests') {  //Unit testing steps go here
    //     bat '"C:\\Program Files (x86)\\NUnit.org\\nunit-console\\nunit3-console.exe" ./LandingPageSvc.Test/bin/Debug/LandingPageSvc.Tests.dll --result nunit-result.xml'
    // }
 //bat "workspace/${env.JOB_NAME}/${env.BRANCH_NAME}/OES-v0.4/OQS.sln"
 //sh "${mvnHome}/bin/mvn clean verify -B"  
  }
  if (currentBranch('master')) {
   stage ('Checkout') {
   checkout scm
   }
    //def mvnHome = tool 'maven-3.0.5'
	   
  stage('Build') {  //Build steps go here
    sh "/DevOps/maven/apache-maven-3.3.9/bin/mvn clean install"
    } 

  }
  }