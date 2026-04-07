pipeline {
agent any // Use any available agent
tools {
maven 'Maven' // Ensure this matches the name
configured inJenkins
}
stages {
stage('Checkout') {
steps {
git branch: 'master', url: '<repo link>'
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
sh 'java -jar target/MyMavenApp-1.0-SNAPSHOT.jar'
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
