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

    stages {
        stage ('Compile Stage') {

            steps {
               
                    sh 'mvn clean compile'
                
            }
        }

        stage ('Testing Stage') {

            steps {
               
                    sh 'mvn test'
                
            }
        }


        stage ('Deployment Stage') {
            steps {
               
                    sh 'mvn deploy'
                
            }
        }
    }
}
