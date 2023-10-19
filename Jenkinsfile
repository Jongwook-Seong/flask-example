node {
     stage('Clone repository') {
         checkout scm
     }
     stage('Build image') {
         app = docker.build("ypwa121/flask-example")
         
     }
     stage('Push image') {
          docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
               app.push("${env.BUILD_NUMBER}")
               app.push("latest")
          }
     }
}

stage('Build image') {
     app = docker.build("ypwa121/flask-example")
}

stage('Push image') {
     docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
          app.push("${env.BUILD_NUMBER}")
          app.push("latest")
     }
}

#stage('Push image') {
#     docker.withRegistry('https://54.197.19.111', 'harbor_cred') {
#          app.push("${env.BUILD_NUMBER}")
#          app.push("latest")
#     }
#}
