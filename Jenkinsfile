node {
  stage('SCM') {
    checkout scm
  }

  stage('Copy App.js') {
    // Copy the app.js file to the workspace
    sh "cp /home/ubuntu/ebux_node_apis/app.js ."
  }

  stage('SonarQube Analysis') {
    def scannerHome = tool 'Sonarqube'
    withSonarQubeEnv() {
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}

