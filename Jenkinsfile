Webapp{
  checkout scm
  
  docker.withRegistry('https://registry.hub.docker.com', 'DockerHub') {
    def customImage = docker.build("krishna1708/minor_test1")
    /*push the container to custom registry*/
    customImage.push()
  }
}
