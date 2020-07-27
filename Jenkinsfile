// https://blog.4linux.com.br/criando-pipelines-no-jenkins-com-jenkinsfile/
pipeline {

    agent any // defini qual agente irá executar o pipeline. any -> primeiro ambiente disponível (Jenkins Master - Própria máquina)

    stages {
        stage('Clone') {
            steps {
                checkout scm
            }
        }
        stage('Clean') {
            steps {
                echo "./mvnw clean"
            }
        }
        stage("Build") {
            steps {
                echo "./mvnw package -x test"
            }
        }
        stage('Test') {
            steps {
                echo "./mvnw test"
                step([$class: "JUnitResultArchiver", testResults: "**/target/surefire-reports/TEST-*.xml"])
            }
        }
    }
}