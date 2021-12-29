node{
def mavenHome = tool name: "maven3.8.4"

properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5')), [$class: 'RebuildSettings', autoRebuild: false, rebuildDisabled: false], [$class: 'JobLocalConfiguration', changeReasonComment: ''], pipelineTriggers([pollSCM('''* * * * *
''')])])

stage('CheckoutCode'){

git branch: 'development', credentialsId: 'dfedefa7-a735-4da1-96d2-eb5432d6e0d5', url: 'https://github.com/Raghunath6169/maven-web-application.git'
}

stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
} 

/*
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"

}

stage('UploadArifactsIntoNexus'){
sh "${mavenHome}/bin/mvn deploy"
}

stage('DeployAppintoTomcatServer'){

sshagent(['d23ecdf9-b2ae-4bb3-9c65-f4aa287238ce']) {
  sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@54.79.136.76:/opt/apache-tomcat-9.0.56/webapps/"
 
}
}

stage('SendEmailNotificaton'){

emailext body: '''Build Over..

Regards,
Raghunath Technologies,
8639317060''', subject: 'Build Over', to: 'nraghunath9052@gmail.com'
}
*/
}







