node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'Maven';
    withSonarQubeEnv() {
      mvn clean verify sonar:sonar \
  -Dsonar.projectKey=devsecops \
  -Dsonar.projectName='devsecops' \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.token=sqp_e565bcb20d67fd765a7d2a87e66add3f5b9c380d
    }
  }
}
