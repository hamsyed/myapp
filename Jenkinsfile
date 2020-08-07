node{
stage('scm checkout'){
     git 'https://github.com/hamsyed/myapp.git'
     }
     }
stage('compile and package'){
     sh 'mvn clean test package'
     tool name: 'maven3', type: 'maven'
     }
}     
