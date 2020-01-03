#!/usr/bin/env groovy

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'git clone https://github.com/spring-projects/spring-petclinic.git'
		sh 'cd spring-petclinic'
		sh 'pwd'
		sh './mvnw package'
		sh 'java -jar target/*.jar'
            }
        }
    }
}
