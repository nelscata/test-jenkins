#!/usr/bin/env groovy

pipeline {
    agent { docker 'maven:3.6-alpine' }
    stages {
        stage('Build') {
            steps {
                sh 'git clone https://github.com/spring-projects/spring-petclinic.git'
		sh 'cd spring-petclinic'
		sh './mvnw package'
		sh 'java -jar target/*.jar'
            }
        }
    }
}
