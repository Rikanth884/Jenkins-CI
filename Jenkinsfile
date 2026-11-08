pipeline {

    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Cloning GitHub Repository...'
                checkout scm
            }
        }

        stage('Compile Java Program') {
            steps {
                echo 'Compiling Java Application...'

                sh 'mkdir -p out'

                sh 'javac -d out src/HelloWorld.java'
            }
        }

        stage('Execute Java Program') {
            steps {
                echo 'Executing Java Application...'

                sh 'java -cp out HelloWorld'
            }
        }
    }

    post {
        success {
            echo 'BUILD SUCCESSFUL!'
        }

        failure {
            echo 'BUILD FAILED!'
        }
    }
}
