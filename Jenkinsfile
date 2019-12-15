pipeline {
  agent {
    node { 
      label: 'ubuntu_node1'
    }
  }
  tools {
    maven 'maven-3.6.3'
  }
  stages {
    stage ('Checkout') {
      steps {
        echo "Cloning git repo."
        git https://github.com/steve-brown701/my-project.git
      }
    }
    stage ('Build') {
      steps {
       sh 'mvn clean compile'
      }
    }
    stage ('Test') {
      steps {
       sh 'mvn test'
       junit '**/target/surefire-reports/TEST-*.xml'
      }
    }
    stage ('Package') {
      steps {
       sh 'mvn package'
      }
    }
  }
}
