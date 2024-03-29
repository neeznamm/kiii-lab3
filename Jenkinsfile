node {
  def app
  stage('Clone repository') {
    checkout scm
  }
  stage('Build image') {
    app = docker.build("neeznamm/kiii-lab3")
  }
  stage('Push image') {
    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
      app.push("${env.BRANCH_NAME}-${env.BUILD-NUMBER}")
      app.push("${env.BRANCH_NAME}-latest")
    }
  }
}
