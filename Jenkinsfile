pipeline {
 agent any // Use any available agent
 tools {
 maven 'Maven' // Ensure this matches the name
 }
 stages {
 stage('Checkout') {
 steps {
 git branch: 'master', url: 'https://github.com/omkarmaha1620-collab/mvn-last4'
 }
 }
 stage('Build') {
 steps {
 sh 'mvn clean package' // Run Maven build
 }
 }
 stage('Test') {
 steps {
 sh 'mvn test' // Run unit tests
 }
 }



 stage('Run Application') {
 steps {
 // Start the JAR application
 sh 'java -jar target/omkar-1.0-SNAPSHOT.jar'
 }
 }

 }
 post {
 success {
 echo 'Build and deployment successful!'
 }
 failure {
 echo 'Build failed!'
 }
 }
}
