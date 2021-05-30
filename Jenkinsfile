pipeline {
  agent {
    node {
      label 'Node1'
    }

  }
  stages {
    stage('File Generation') {
      steps {
        retry(count: 1)
        sh 'echo -e "FROM  centos:7\\nRUN yum install httpd -y\\nRUN echo Hello >/var/www/html/index.html" > Dockerfile'
      }
    }

    stage('Building Image') {
      steps {
        retry(count: 1)
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