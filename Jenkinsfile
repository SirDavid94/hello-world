pipeline {
    agent any
    tools {
        maven "MAVEN"
        jdk "JDK"
    }
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
