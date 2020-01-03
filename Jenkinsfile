#!/usr/bin/env groovy
node {
    stage 'Clone the project'
    git 'https://github.com/spring-projects/spring-petclinic'
   
    dir('spring-petclinic') {
        stage("Compilation and Analysis") {
            parallel 'Compilation': {
                sh "./mvnw package"
            }, 'Static Analysis': {
                stage("Checkstyle") {
                    sh "./mvnw checkstyle:checkstyle"
                     
                    step([$class: 'CheckStylePublisher',
                      canRunOnFailed: true,
                      defaultEncoding: '',
                      healthy: '100',
                      pattern: '**/target/checkstyle-result.xml',
                      unHealthy: '90',
                      useStableBuildAsReference: true
                    ])
                }
            }
        }
    }
}
