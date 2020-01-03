#!/usr/bin/env groovy

node {
 
    git url: 'https://github.com/spring-projects/spring-petclinic.git'
 
    // install Maven and add it to the path
    env.PATH = "${tool 'M3'}/bin:${env.PATH}"
 
    configFileProvider(
        [configFile(fileId: 'maven-settings', variable: 'MAVEN_SETTINGS')]) {
        sh 'mvn -s $MAVEN_SETTINGS clean package'
    }
 
}
