// https://blog.4linux.com.br/criando-pipelines-no-jenkins-com-jenkinsfile/
pipeline {

    agent any // defini qual agente irá executar o pipeline. any -> primeiro ambiente disponível (Jenkins Master - Própria máquina)

    stages {
        stage('Clone') {
            checkout scm
        }
        stage('Clean') {
            sh "./mvnw clean"
        }
        stage("Build") {
            sh "./mvnw package -x test"
        }
        stage('Test') {
            sh "./mvnw test"
            step([$class: "JUnitResultArchiver", testResults: "**/target/surefire-reports/TEST-*.xml"])
        }
    }
}