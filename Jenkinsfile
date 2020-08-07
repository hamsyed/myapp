node{
stage('scm checkout'){
     git 'https://github.com/hamsyed/myapp.git'
     }
stage('compile and package'){
    
     def mvn_HOME = tool name: 'maven3', type: 'maven'
     sh '${mvn_HOME}\bin mvn clean test package'
     
     }
}     
