pipeline {
    agent any
    environment {
        JAVA_HOME = 'C:\\Program Files\\Java\\jdk-17'
        PYTHON_HOME = 'C:\\Users\\User\\AppData\\Local\\Programs\\Python\\Python313'
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
                        sh 'hello_world.py'
                    } else {
                        bat 'echo "Running on Windows"'
                        bat 'javac HelloWorld.java'
                        bat 'java HelloWorld'
                        bat 'python hello_world.py'
                    }
                }
            }
        }
    }
}