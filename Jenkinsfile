pipeline {
  agent any
  tools {
    gradle 'gradle-4.5.1'
    jdk 'java8'
    }
  stages {
    stage('Checkout') {
      steps {
        git branch: 'main', url: 'https://github.com/djadk84/java_lib.git'
        }
      }
    stage('Build') {
      steps {
        sh 'gradle clean build'
        junit 'build/test-results/**/TEST-*.xml'
        }
      }
    stage('Deploying to Staging') {
      steps {
        echo "Deploying to staging"
        }
      }
    stage('Deploying to Production') {
      when {
        not {
           branch 'feature'
          }
        }
      steps {
        echo "Deploying to production"
        }
      }
    }
  }