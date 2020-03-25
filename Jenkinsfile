node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube analysis') {
    def scannerHome = tool 'SonarScanner 4.0';
    withSonarQubeEnv('sonar-1') { 
      sh "${scannerHome}/bin/sonar-scanner"
    }
  }
}
