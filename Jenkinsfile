pipeline {
    agent any
    environment {
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-17'
        PYTHON_HOME = 'C:\\Users\\User\\Documents\\python313'
        PATH = "${env.PATH};${JAVA_HOME}\\bin;${PYTHON_HOME}"
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning the repository...'
                git branch: 'main', url: 'https://github.com/NAFHIFOUAD/MonProjetJenkins.git'
            }
        }
        stage('Build and Run') {
            steps {
                script {
                    if (isUnix()) {
                        echo 'Running on Unix-based system'
                        sh 'javac HelloWorld.java'
                        sh 'java HelloWorld'
                        sh 'python3 hello_world.py'
                    } else {
                        echo 'Running on Windows'
                        bat 'javac HelloWorld.java'
                        bat 'java HelloWorld'
                        bat 'python hello_world.py'
                    }
                }
            }
        }
    }
}
