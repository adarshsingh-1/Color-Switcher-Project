pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages {
    stage("Cleanup Workspace") {
      steps {
        cleanWs()
      }
    }
    stage("Checkout from SCM") {
      steps {
        git branch: 'main', 
            credentialsId: 'github', 
            url: 'https://github.com/adarshsingh-1/Color-Switcher-Project'
      }
    }
    stage("Build Application") {
      steps {
        // **FIX:** Change directory to where pom.xml is located
        dir('Color-Switcher-Project') {
          sh "mvn clean package"
        }
      }
    }
    stage("Test Application") {
      steps {
        // **FIX:** Also change directory here for the test stage
        dir('Color-Switcher-Project') {
          sh "mvn test"
        }
      }
    }
  }
}
