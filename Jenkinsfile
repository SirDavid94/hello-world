pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean install'
             }
        }
        stage('Copy Artifacts') {
            steps {
                sh 'scp root@172.31.8.27:$WORKSPACE/webapp/target/webapp.war /opt/docker'
                sh 'ansible-playbook /opt/docker/create_image_regapp.yml'
             }
          } 
    }
}
