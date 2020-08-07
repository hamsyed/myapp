node{
stage('scm checkout'){
     git 'https://github.com/hamsyed/myapp.git'
     }
stage('compile and package'){
    
     def mvn_HOME = tool name: 'maven3', type: 'maven'
     sh "${mvn_HOME}/bin/mvn clean test package"
     
     }
     
 stage('Email Notification'){    
     mail bcc: '', body: '''Hi Welcome to jenkins email alert
thanks
hameed''', cc: '', from: '', replyTo: '', subject: 'test-jenkins', to: 'syed.hameed.uddin@gmail.com'
     }
}     
