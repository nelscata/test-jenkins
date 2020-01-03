#!/usr/bin/env groovy
pipeline {
   agent any

   
   def mvnHome
   tools {
      // Install the Maven version configured as "M3" and add it to the path.
      //maven "M3"
      mvnHome = tool 'M3'
   }

   stages {
      stage('Build') {
         steps {
            // Get some code from a GitHub repository
            git 'https://github.com/spring-projects/spring-petclinic'

            //sh "mvn -Dmaven.test.failure.ignore=true clean package"
	    sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"

         }

         post {
            // If Maven was able to run the tests, even if some of the test
            // failed, record the test results and archive the jar file.
            success {
               junit '**/target/surefire-reports/TEST-*.xml'
               archiveArtifacts 'target/*.jar'
            }
         }
      }
   }
}
