pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo "Checking Docker"
                bat "where docker"
                bat "docker --version"
                bat "docker build -t week7 ."
            }
        }

        stage('Run') {
            steps {
                echo "Run application in Docker Container"
                bat "docker rm -f mycontainer || exit 0"
                bat "docker run -d -p 5000:5000 --name mycontainer mypythonflaskapp"
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Please check the logs.'
        }
    }
}
