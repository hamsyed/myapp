node{
    stage('git checkout'){
    git 'https://github.com/hamsyed/myapp.git'
    }
    stage('compile-code'){    
    def mvnHOME = tool name: 'MAVEN_HOME', type: 'maven'
        sh "${mvnHOME}/bin/mvn clean test package"
    }
    stage('Email notification'){
    mail bcc: '', body: '''hello,
    please verify the job failed again ::::::

    regards
    ''', cc: '', from: '', replyTo: '', subject: 'Jenkins-testing', to: 'syed.hameed.uddin@gmail.com'
    }    
}
