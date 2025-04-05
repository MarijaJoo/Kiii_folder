node{
 def app
 stage('Clone repository'){
  checkout scm
}
 stage('Build image'){
  app=docker.build("marijajoo/Kiii_folder")
}
 stage('Push image'){
  docker.withRegistry('https://registry.hub.docker.com','dockerhub'){
   app.push("${env.BRANCH_NAME}-${ENV.BUILD_NUMBER}")
   app.push("${env.BRANCH_NAME}-latest")
}
}
}