pipeline {
  agent any
  tools {
    gradle 'gradle-4.5.1'
    }
  stages {
    stage('Checkout') {
      steps {
        git branch: 'feature/bestcodeyet', url: 'https://github.com/djadk84/java_lib.git'
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
        branch 'main'
        }
      steps {
        echo "Deploying to production"
        }
      }
    }
  }