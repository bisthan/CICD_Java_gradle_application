pipeline{
    agent any
       stages{
           stage('sonar code analyser'){
              agent {
                  docker {
                      image 'openjdk:11'
                  }
              }

                steps{
                    scrips{
                        waitForQualityGate abortPipeline: false, credentialsId: 'sonar-config'
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'

                    }
                }

           }
           
       }
}