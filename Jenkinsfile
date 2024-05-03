#! /usr/bin/env groovy
pipeline {
    agent any

    tools {

        maven 'Maven'

    }

    environment {

        NAME = 'GUIDO'

    }



    stages {

        stage('init') {
            steps {
                echo 'Initialize job...'
                sh 'mvn --version'
            }
        }

        stage('echoVars') {



            when {
                environment name :'NAME' , value :'GUIDO'
            }

            steps {

              echo "print vars..."
              echo "$NAME"

            }
        }

        stage('params') {

            input{
                message 'Should we proceed?'
                ok 'Yes we do!'

                parameters {

                    string(name:'Tipo',defaultValue:'env', description:'Che tipo è???')

                }
            }

            steps {

              echo "tipo: ${Tipo}"

            }
        }

    }

    post {

            always {

                echo "Job successful!!!"
            }

        }
}
