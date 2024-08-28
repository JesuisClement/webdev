node {
  def app
  stage('Clone repository') {
    checkout scm  
  }
  stage('Build image') {
    app = docker.build("clemzer/j3-webdev") 
  }
  stage('Push image') {
    docker.withRegistry('https://registry.hub.docker.com', 'docker-credentials') {
      app.push("latest")
    }  
  }
}
