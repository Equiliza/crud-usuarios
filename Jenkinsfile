pipeline {
    agent any

    stages {
        stage('Compile') {
            steps {
                script {
                    dir ("C:/Users/Patricia Ortiz/Desktop/Ejercicio/ejemplo-maven") {
                        bat "./mvnw.cmd clean compile -e"                       
                    }
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    dir ("C:/Users/Patricia Ortiz/Desktop/Ejercicio/ejemplo-maven") {
                        bat "./mvnw.cmd clean test -e"                       
                    }
                }
            }
        }
        stage('Jar') {
            steps {
                script {
                    dir ("C:/Users/Patricia Ortiz/Desktop/Ejercicio/ejemplo-maven") {
                        bat "./mvnw.cmd clean package -e"                       
                    }
                }
            }
        }
        stage('Run') {
            steps {
                script {
                    dir ("C:/Users/Patricia Ortiz/Desktop/Ejercicio/ejemplo-maven") {
                        bat "nohup bash mvnw spring-boot:run &"
                        sleep 20
                    }
                }
            }
        }
        stage('TestApp') {
            steps {
                script {
                    bat "start chrome http://localhost:8081/rest/mscovid/test?msg=testing"
                }
            }
        }
    }
}

