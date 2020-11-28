 
pipeline {
    agent any

    stages {
        stage('compile') {
            steps {
                dir("/Users/andres/Desktop/DevOps/ejemplo-maven"){
                    sh './mvnw clean compile -e'
                }
            }
        }
        stage('Test Code') {
            steps {
                dir("/Users/andres/Desktop/DevOps/ejemplo-maven"){
                    sh './mvnw clean test -e'
                }
            }
        }
        stage('Jar Code') {
            steps {
                dir("/Users/andres/Desktop/DevOps/ejemplo-maven"){
                    sh './mvnw clean package -e'
                }
            }
        }
        stage('Run Jar') {
            steps {
                dir("/Users/andres/Desktop/DevOps/ejemplo-maven"){
                    sh 'nohup bash mvnw spring-boot:run &'
                    sleep 20
                    sh 'curl -X GET http://localhost:8081/rest/mscovid/test?msg=testing'
                }
            }
        }
        
    }
}
