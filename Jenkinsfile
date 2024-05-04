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



            steps {

              echo "stampa params"

            }
        }

    }

    post {

            always {

                echo "Job hooks!!!"
            }

        }
}
