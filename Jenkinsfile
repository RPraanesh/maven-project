pipeline {
agent any
stages {
stage('CodeCheckout') {
steps {
script {
checkout scm
def mvnHome = tool 'maven-1'
}
}
}
stage('Build Maven App') {
steps {
script {
checkout scm
def mvnHome = tool 'maven-1'
try {
sh "mvn clean install"
currentBuild.result = 'Success'
} catch (Exception err) {
currentBuild.result = 'FAILURE'
sh "exit 1"
sh "java -version"
}
}}
}
