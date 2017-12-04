pipeline {
  agent any
  stages {
    stage('Deploy') {
      steps {
        echo '.....Deploying.....'
      }
    }
    stage('Test') {
      parallel {
        stage('Test') {
          steps {
            echo '.....Testing.....'
          }
        }
        stage('RunWindowsBatchScript') {
          steps {
            bat(returnStdout: true, returnStatus: true, script: 'TestBatchScript1')
          }
        }
        stage('RunShellScript') {
          steps {
            echo "-----sh commented-----" //#sh 'aaa="Hello"; bbb=" World"; echo $aaa$bbb >> aaabbb.txt'
          }
        }
      }
    }
    stage('Build') {
      steps {
        echo '.....Build.....'
      }
    }
  }
}

