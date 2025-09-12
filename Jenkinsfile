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
    // The "Checkout" stage has been removed because Jenkins handles it automatically
    
    stage("Build Application") {
      steps {
        // Run the maven command from the project root
        sh "mvn clean package"
      }
    }
    stage("Test Application") {
      steps {
        // Run the maven command from the project root
        sh "mvn test"
      }
    }
  }
}

