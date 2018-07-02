def label = "pl_declarative_docker_dnd-${UUID.randomUUID().toString()}"
pipeline {
  agent {
    kubernetes {
      //cloud 'kubernetes'
      label "${label}
      containerTemplate {
        name 'maven'
        image 'maven:3.3.9-jdk-8-alpine'
        ttyEnabled true
        command 'cat'
      }
    }
  }
  stages {
    stage('Run maven') {
      steps {
        container('maven') {
          sh 'mvn -version'
        }
      }
    }
  }
}
