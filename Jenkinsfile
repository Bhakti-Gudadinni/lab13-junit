pipeline {
agent any
tools {
jdk 'JDK17'
maven 'Maven3'
}
stages {
stage('Checkout') {
steps {
git '<repo-url>'
}
}
stage('Build & Test') {
steps {

sh 'mvn clean test'
}
}
}
post {
always {
junit '**/target/surefire-reports/*.xml'
}
}
}
