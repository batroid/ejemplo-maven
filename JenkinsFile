pipeline {
    agent any

    stages {
        stage('compile') {
            steps {
                dir("/Users/andres/Desktop/DevOps/proyectos/ejemplo-maven"){
                    sh './mvnw clean compile -e'
                }
            }
        }
        stage('Test Code') {
            steps {
                dir("/Users/andres/Desktop/DevOps/proyectos/ejemplo-maven"){
                    sh './mvnw clean test -e'
                }
            }
        }
        stage('Jar Code') {
            steps {
                dir("/Users/andres/Desktop/DevOps/proyectos/ejemplo-maven"){
                    sh './mvnw clean package -e'
                }
            }
        }
        stage('Run Jar') {
            steps {
                dir("/Users/andres/Desktop/DevOps/proyectos/ejemplo-maven"){
                    sh 'nohup bash mvnw spring-boot:run &'
                }
            }
        }
        stage('Testing Application') {
            steps {
                dir("/Users/andres/Desktop/DevOps/proyectos/ejemplo-maven"){
                    sh 'curl -X GET http://localhost:8081/rest/mscovid/test?msg=testing'
                }
            }
        }
    }
}
