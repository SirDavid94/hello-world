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
                sshagent (credentials: ['EC2_user']) {
                    sh 'scp -o StrictHostKeyChecking=no webapp/target/webapp.war ec2-user@172.31.80.154:/opt/docker'
                    sh 'ssh -o StrictHostKeyChecking=no ec2-user@172.31.80.154; cd /opt/docker; ansible-playbook /opt/docker/create_image_regapp.yml;'
                }
             }
          } 
    }
}
