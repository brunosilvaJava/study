// https://blog.4linux.com.br/criando-pipelines-no-jenkins-com-jenkinsfile/
pipeline {

    agent any // defini qual agente irá executar o pipeline. any -> primeiro ambiente disponível (Jenkins Master - Própria máquina)

    stages {
        stage('Stage 1') {
            steps {
                echo "Executando stage 1"
            }
        }
        stage('Stage 2') {
            steps {
                echo "Executando stage 2"
            }
        }
    }
}