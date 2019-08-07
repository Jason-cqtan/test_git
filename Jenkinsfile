pipeline {
  agent {
    node {
      label 'dev'
    }

  }
  stages {
    stage('git') {
      steps {
        dir(path: '/root/projects/test_git') {
          git(url: 'https://github.com/Justin-jc/test_git.git', credentialsId: 'login-github', poll: true)
        }

      }
    }
    stage('build') {
      steps {
        sh 'sudo -H pip install -r requirements.txt'
      }
    }
    stage('run') {
      steps {
        sh 'python app.py'
      }
    }
  }
}