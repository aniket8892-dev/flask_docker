node {
   stage('Code_Pull') {
      // copy source code from local file system and test
      // for a Dockerfile to build the Docker image

      git branch: "main", url: 'https://github.com/aniket8892-dev/flask_docker.git'
      if (!fileExists("Dockerfile")) {
         error('Dockerfile missing.')
      }
   }
   stage('Build Docker') {
       // build the docker image from the source code using the BUILD_ID parameter in image name
         sh "sudo docker build -t flask-app ."
   }
   stage("run docker container"){
        sh "sudo docker run -p 8000:8000 --name flask-app -d flask-app "
    }
}
