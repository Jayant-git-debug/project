pipeline {
  agent any
  stages {
    stage('Build on Remote') {
      steps {
        sshagent(['c55758a5-d427-462f-ae84-7786d7442c0c']) {
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
