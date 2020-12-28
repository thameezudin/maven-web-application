node ('master')
 {

  def mavenHome = tool name: "maven3.6.2"

      echo "GitHub BranhName ${env.BRANCH_NAME}"
      echo "Jenkins Job Number ${env.BUILD_NUMBER}"
      echo "Jenkins Node Name ${env.NODE_NAME}"

      echo "Jenkins Home ${env.JENKINS_HOME}"
      echo "Jenkins URL ${env.JENKINS_URL}"
      echo "JOB Name ${env.JOB_NAME}"

   properties([[$class: 'JiraProjectProperty'], buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '2', daysToKeepStr: '', numToKeepStr: '2')), pipelineTriggers([pollSCM('* * * * *')])])

  stage("CheckOutCodeGit")
  {
   git 'https://github.com/thameezudin/maven-web-application.git'
}

 stage("Build")
 {
 sh "${mavenHome}/bin/mvn clean package"
 }

 
 }

