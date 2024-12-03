
pipeline {
    agent any
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
                        withEnv([
                            "JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64",
                            "PYTHON_HOME=/usr/bin",
                            "PATH=${env.PATH}:${JAVA_HOME}/bin:${PYTHON_HOME}"
                        ]) {
                            sh 'echo "Running on Unix"'
                            sh 'javac HelloWorld.java'
                            sh 'java HelloWorld'
                            sh 'python hello_world.py'
                        }
                    } else {
                        withEnv([
                            "JAVA_HOME=C:\\Program Files\\Java\\jdk-17",
                            "PYTHON_HOME=C:\\Users\\User\\Documents\\python313",
                            "PATH=${env.PATH};${JAVA_HOME}\\bin;${PYTHON_HOME}"
                        ]) {
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
}