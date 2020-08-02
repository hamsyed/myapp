node{
    stage('git checkout'){
    git 'https://github.com/hamsyed/myapp.git'
    }
    stage('compile-code'){    
    def mvnHOME = tool name: 'MAVEN_HOME', type: 'maven'
        sh "${mvnHOME}/bin/mvn clean test package"
    }
}
