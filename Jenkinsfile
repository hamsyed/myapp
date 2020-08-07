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
}     
