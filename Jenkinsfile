pipeline {
  agent { label 'Jenkins-Agent' }

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

    stage("Build/Validate") {
      steps {
        echo "No build needed for static project. Validating files..."
        sh "ls -l"
      }
    }

    stage("Deploy") {
      steps {
        echo "Deploy step goes here (e.g., copy files to web server, S3, or Docker image)"
      }
    }
  }
}
