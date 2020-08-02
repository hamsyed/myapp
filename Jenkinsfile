node {
    stage {'git checkout'} {
    git 'https://github.com/hamsyed/myapp.git'
    }
    stage {'compile-code'}{
    tool name: 'MAVEN_HOME', type: 'maven'
    sh 'clean test package'
    }
}
