pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                dir("/var/lib/jenkins/workspace/$WORKSPACE/") {
                sh 'mvn clean install'
                }
          } 
        }
  }
}
