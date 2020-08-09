node{
stage('scm checkout'){
     git 'https://github.com/hamsyed/myapp.git'
     }
stage('compile and package'){
    
     def mvn_HOME = tool name: 'maven3', type: 'maven'
     sh "${mvn_HOME}/bin/mvn clean test package"
     
     }
     
  //stage('Email Notification'){    
  //  mail bcc: '', body: '''Hi,
  //  welcome to jenkins -pipeline testing 
  //  regards
  //  Hameed''', cc: '', from: 'hameed syed', replyTo: '', subject: 'Jenkin test mail ', to: 'syed.hameed.uddin@gmail.com'
  //   }
 stage('SonarQube analysis') {
     def mvn_HOME = tool name: 'maven3', type: 'maven'
     withSonarQubeEnv('sonar-6') { // If you have configured more than one global server connection, you can specify its name
      sh "${mvn_HOME}/bin/mvn sonar:sonar"
    }
  }
     // No need to occupy a node
stage("Quality Gate"){
    timeout(time: 1, unit: 'HOURS') { // Just in case something goes wrong, pipeline will be killed after a timeout
    def qg = waitForQualityGate() // Reuse taskId previously collected by withSonarQubeEnv
    if (qg.status != 'OK') {
      error "Pipeline aborted due to quality gate failure: ${qg.status}"
    }
  }
}
sshagent(['tomcat-dev']) {
    sh 'scp -o StrictHostKeyChecking=no target/*.war ubuntu@172.31.33.71:/opt/tomcat8/webapps/'
}     
}     
