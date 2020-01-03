#!/usr/bin/env groovy

node {
 
    withMaven(maven:'maven') {
 
        stage('Checkout') {
            git url: 'https://github.com/spring-projects/spring-petclinic', credentialsId: 'nelscata', branch: 'master'
        }
 
        stage('Build') {
            sh 'mvn clean install'
 
            def pom = readMavenPom file:'pom.xml'
            print pom.version
            env.version = pom.version
        }
    }
}
