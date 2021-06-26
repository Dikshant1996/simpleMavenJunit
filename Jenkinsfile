pipeline {
  agent any
  stages {
    stage('Code from SCM') {
      steps {
        git(url: 'https://github.com/Dikshant1996/simpleMavenJunit.git', changelog: true, poll: true)
      }
    }

    stage('compile') {
      steps {
        sh '''mvn clean
'''
      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

    stage('build package') {
      steps {
        sh 'mvn package'
      }
    }

    stage('publish report') {
      steps {
        junit 'target/surefire-reports/*xml'
      }
    }

  }
}