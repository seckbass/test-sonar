node {
  stage('SCM') {
    checkout scm
  }

  stage('compile'){
	sh 'mvn package'
  }

  stage('SonarQube analysis') {
    withSonarQubeEnv('sonar-1') { 
      sh 'mvn sonar:sonar'
    }
  }
}
