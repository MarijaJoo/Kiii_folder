node{
 def app
 stage('Clone repository'){
  checkout scm
}
 if (ENV.BRANCH_NAME=='deev'){
 stage('Build image'){
  app=docker.build("marijajoo/kiii_folder")
}
 stage('Push image'){
  docker.withRegistry('https://registry.hub.docker.com','dockerhub'){
   app.push("${env.BRANCH_NAME}-${ENV.BUILD_NUMBER}")
   app.push("${env.BRANCH_NAME}-latest")
}
 }
}
 else{
  echo "The Docker Image build and push to Docker Hub will only happen if the changes are on the ‘dev’ branch."
 }
}
