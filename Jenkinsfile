node{
    stage {'git checkout'}{
    git 'https://github.com/hamsyed/myapp.git'
    }
    stage {'compile-code'}{
    sh 'mvn clean test package'
    }
}
