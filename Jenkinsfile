#!/usr/bin/env groovy

pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'git clone https://github.com/spring-projects/spring-petclinic.git'
		sh 'cd spring-petclinic'
		def mvnHome = tool name: 'Maven 3.6.3', type: 'maven'
		sh "${mvnHome}/bin/mvn package"
		sh 'java -jar target/*.jar'
            }
        }
    }
}
