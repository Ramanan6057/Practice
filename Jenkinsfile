pipeline {
  agent any

  stages {
    stage('Clone Repo') {
      steps {
        git branch: 'main', url: 'https://github.com/Ramanan6057/Practice.git'
      }
    }

    stage('Run Script') {
      steps {
        sh '''
          chmod +x runme.sh
          ./runme.sh > output.txt
        '''
      }
    }

    stage('Archive Output') {
      steps {
        archiveArtifacts artifacts: 'output.txt', fingerprint: true
      }
    }
  }
}
