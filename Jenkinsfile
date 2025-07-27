node {
  stage('SCM Checkout') {
    git url: 'https://github.com/ostronaut1/survey-website-jenkins-test.git', branch: 'main'
  }
  stage('Compile-Package') {
    // Get maven home
    def mvnHome = tool name: 'maven-3', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }
  stage('Archive') {
    archiveArtifacts artifacts: 'target/*.jar', allowEmptyArchive: true
  }
}
