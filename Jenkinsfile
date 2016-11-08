#!groovy
node {
  stage ('Checkout') {
   sh  'git clone https://github.com/AndreasZeissner/pipeline_backend ./build-go-backend'
  }
  stage ('Build') {
   sh 'docker build -t go/lang-backend ./build-go-backend'
  }
  stage('RunDockerOnPort') {
   sh 'docker stop fhws_backend'
   sh 'docker rm fhws_backend'
   sh 'docker run --name=fhws_backend -d -p 8083:8083 go/lang-backend'
  }
  stage ('CleanUp') {
   sh 'rm -r ./build-go-backend'
  }
}
