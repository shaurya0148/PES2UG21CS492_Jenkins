pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Compile the .cpp file using a shell script
                sh 'ls'
                build 'PES2UG21CS492-1'
                sh 'g++ -o obj main/hello.cpp'
            }
        }

        stage('Test') {
            steps {
                // Intentionally introduce an error in the Test stage
                sh 'exit 1'
            }
        }

        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }

    post {
        failure {
            echo 'Pipeline failed'
        }
    }
}
