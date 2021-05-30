pipeline {
  agent any
  stages {
    stage('File Generation') {
      steps {
        sh 'echo -e "FROM  centos:7\\nRUN yum install httpd -y\\nRUN echo Hello >/var/www/html/index.html" > Dockerfile'
      }
    }

    stage('Building Image') {
      steps {
        sh 'docker build -t myimage .'
      }
    }

    stage('Verify images') {
      steps {
        sh 'docker images | grep myimage'
      }
    }

  }
}