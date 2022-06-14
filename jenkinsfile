node{
def mavenHome = tool name: "maven3.8.4"
properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('* * * * *')])])
stage('Checkoutcode')
{
git branch: 'development', credentialsId: 'eb8b0398-47e4-4656-a3f8-ec9b0d7b22d4', url: 'https://github.com/sai-mithunfork/maven-web-application.git'
}
stage('Build')
{
sh "${mavenHome}/bin/mvn clean package"
//if you installed mvn in window then we need to use "bat" in the place of sh 

}
/*
stage('ExecuteSonarQubeReport')
{
sh "${mavenHome}/bin/mvn sonar:sonar"
}
stage('UploadArtifactsIntoNexus')
{
sh "${mavenHome}/bin/mvn deploy"
}
stage('DeployAppIntoTomcatServer')
{
sshagent(['13ef7370-c8e3-4b2f-9bde-10154062d7ab']) {
sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.38.59:/opt/apache-tomcat-9.0.63/webapps"
}
} 
*/
}

