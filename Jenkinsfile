pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage('Build') {
            steps {
               sh"mvn clean compile"
            }
        }


         stage('Test') {
              parallel {
               stage('Unit') {
                  steps {
                            sh 'mvn test'
                          }
                        }

                        stage('Integration') {
                          steps {
                            sh 'mvn verify'
                          }
                        }
         stage('Succes') {
              steps {
                sh 'echo "success"'
              }
            }

    }
}