pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/srecchia26/flask', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'docker build -t srecchia26/flask-app .'
      }
    }

    stage('Docker Login') {
      steps {
        sh 'docker login -u srecchia26 -p dckr_pat_ID3ui64h4uOcivDetZO_M8Qj5K0'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push srecchia26/flask-app'
      }
    }

  }
}