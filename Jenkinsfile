node {
  stage('SCM') {
    checkout scm
  }

  stage('compile'){
	def mvnHome = tool name: 'maven-3', type: 'maven'
	sh "${mvnHome}/bin/mvn package"
  }

  stage('SonarQube analysis') {
    def mvnHome = tool name: 'maven-3', type: 'maven'
    withSonarQubeEnv('sonar-1') { 
      sh "${mvnHome}/bin/mvn sonar:sonar"
    }
  }
}
