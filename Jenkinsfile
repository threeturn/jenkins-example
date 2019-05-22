pipeline {
      agent {
    kubernetes {
      label 'declarative'
      containerTemplate {
        name 'maven'
        image 'maven:3.5.0-jdk-8-alpine'
        ttyEnabled true
        command 'cat'
      }
    }
}
    agent any

    stages {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven_3_5_0') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
