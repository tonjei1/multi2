pipeline{
  agent any
  stages{
    stage('version-control'){
      steps{
        checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[credentialsId: 'https://github.com/tonjei1/multi2.git']]])
      }
    }
    stage('parallel-job'){
      parallel{
        stage('sub-job11'){
          steps{
            echo 'action1'
          }
        }
        stage('sub-job2'){
          steps{
            echo 'action2'
          }
        }
      }
    }
    stage('codebuild'){
      steps{
        sh 'cat /etc/passwd'
      }
    }
  }
}
