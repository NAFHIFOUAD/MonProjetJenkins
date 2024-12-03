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
                git branch: 'main', url: 'https://github.com/NAFHIFOUAD/MonProjetJenkins.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    if (isUnix()) {
                        sh 'echo "Running on Unix"'
                        sh 'javac HelloWorld.java'
                        sh 'java HelloWorld'
                        sh 'python3 hello.py'
                    } else {
                        bat 'echo "Running on Windows"'
                        bat 'javac HelloWorld.java'
                        bat 'java HelloWorld.java'
                        bat 'python hello_word.py'
                    }
                }
            }
        }
    }
}