pipeline {
 agent any
 tools {
 nodejs 'NodeJS 16' // Sesuaikan dengan nama Node.js yang dikonfigurasi di Jenkins
 }
 stages {
 stage('Checkout') {
 steps {
 git branch: 'main', url: https://github.com/rendhrivaalya/node.git
 }
 }
 stage('Install Dependencies') {
 steps {
 sh 'npm install'
 }
 }
 stage('Run Tests') {
 steps {
 sh 'npm test'
 }
 post {
 success {
 junit 'test-results.xml' // Sesuaikan dengan lokasi file hasil tes
 }
 failure {
 echo 'Tests failed!'
 }
 }
 }
 stage('Build') {
 steps {
 sh 'npm run build' // Sesuaikan dengan perintah build di proyek Anda
 }
 }
 stage('Deploy') {
 steps {
 echo 'Deploying to production environment...'
   // Tambahkan perintah deploy sesuai kebutuhan Anda
 }
 }
 }
 post {
 success {
 echo 'Pipeline completed successfully!'
 }
 failure {
 echo 'Pipeline failed!'
 }
 }
}
   
