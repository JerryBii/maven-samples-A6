pipeline {
  agent any
  stages {
    stage('check out') {
      steps {
        git(url: 'https://github.com/JerryBii/maven-samples-A6', branch: 'master')
      }
    }

    stage('run') {
      steps {
        bat 'git bisect start'
        bat 'git bisect good 98ac319c0cff47b4d39a1a7b61b4e195cfa231e5'
        bat 'git bisect bad 198644632661c67b6c32f59e9047c11a70685e15'
        bat 'git bisect run mvn clean test'
      }
    }

  }
  tools {
    maven 'DHT_MVN'
    jdk 'DHT_SENSE'
  }
}