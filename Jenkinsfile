pipeline {
agent any
tools {
maven 'maven'
jdk 'JDK'
}
stages {
stage('Checkout') {
steps {
git branch: ‘master’, url: 'https://github.com/Langerraghav12/mvn.git'
}
}
stage('Build') {
steps {
sh 'mvn clean package'
}
}
stage('Test') {
steps {
sh 'mvn test'
}
}
stage('Run Application') {
steps {
// Start the JAR application
sh 'java -jar target/my-maven1-1.0-SNAPSHOT.jar'
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
