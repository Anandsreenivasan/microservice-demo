#!groovy
//def buildstep = fileLoader.fromGit('buildSteps', gitURL, env.BRANCH_NAME,'', '')
def currentBranch(branchName) {
    return env.BRANCH_NAME == branchName
    }
node ('UnixNode1'){

if (currentBranch('dev')) {
   stage ('Checkout') {
   checkout scm
   }
  stage('Build') {  //Build steps go here
    sh "/DevOps/maven/apache-maven-3.3.9/bin/mvn clean install"
    } 
  }
  if (currentBranch('master')) {
   stage ('Checkout') {
   checkout scm
   }
   stage('Build') {  //Build steps go here
    sh "mvn deploy"
    } 
  }
  }