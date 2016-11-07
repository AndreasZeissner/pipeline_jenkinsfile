#!groovy
node {
  stage ('Checkout') {
   sh  'git clone https://github.com/AndreasZeissner/pipeline_backend ./build-go-backend'
  }
  stage ('Build') {
   sh 'docker build -t go/lang-backend ./build-go-backend'
  }
}
