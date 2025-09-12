pipeline {
  agent { label 'Jenkins-Agent' }
  tools {
    jdk 'Java17'
    maven 'Maven3'
  }
  stages {
    stage("Cleanup Workspace") {
      steps {
        // 1. Clean the workspace first.
        cleanWs()
      }
    }
    stage("Checkout from SCM") {
      steps {
        // 2. Now, check out the code.
        git branch: 'main', 
            credentialsId: 'github', 
            url: 'https://github.com/adarshsingh-1/Color-Switcher-Project'
      }
    }
    stage("Build Application") {
      steps {
        // 3. The pom.xml is now present, so this will work.
        sh "mvn clean package"
      }
    }
    stage("Test Application") {
      steps {
        // 4. This will also work.
        sh "mvn test"
      }
    }
  }
}

