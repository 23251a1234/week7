stage('Build') {
    steps {
        echo "Checking Docker"
        bat "where docker"
        bat "docker --version"
        bat "docker build -t mypythonflaskapp ."
    }
}