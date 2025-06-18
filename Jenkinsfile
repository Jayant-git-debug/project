pipeline {
  agent any
  stages {
    stage('Build on Remote') {
      steps {
        sshagent(['jenkins']) {
          sh '''
            ssh -o StrictHostKeyChecking=no jenkins@172.31.86.33 '
              rm -rf /home/maven/app &&
              git clone -b master https://github.com/Jayant-git-debug/CI-CD.git /home/maven/app &&
              cd /home/maven/app &&
              mvn clean package -DskipTests
            '
          '''
        }
      }
    }
  }
}
