pipeline {
  //agent any
  agent { node { label 'Workstation' } }

  environment {
    TEST_URL = "google.com"
    SSH = credentials("centos-SSH")
  }

  options {
    ansiColor('xterm')
  }

  stages {

    stage('Compile') {
      steps {
        //echo 'Hello World'
        //error 'This is an error'
        echo TEST_URL
        echo SSH
        sh 'env'
        sh 'ansible -i 172.31.30.26, all -e ansible_user=${SSH_USR} -e ansible_password=${SSH_PSW} -m ping'
      }
    }

  }

  post {
    always {
      echo 'Post'
      // Send Email
      // Trigger Some another Job
      // Update some JIRA Status about the build.
    }
  }

}