pipeline {

    agent any

    stages {

        stage ('Build') {
            steps {
                withMaven(maven: 'maven_3_8_5') {
                    bat 'mvnw clean compile'
                    echo 'complie completed'
                }
            }
        }

        stage ('Deploy') {
            steps {

                withCredentials([[$class          : 'UsernamePasswordMultiBinding',
                                  credentialsId   : 'PCF_LOGIN',
                                  usernameVariable: 'USERNAME',
                                  passwordVariable: 'PASSWORD']]) {

                    //bat 'cf login -a https://api.run.pivotal.io -u $USERNAME -p $PASSWORD
                    bat 'cf login -a https://api.run.pivotal.io -u sasikalasadagopanmay08@gmail.com -p Chennai@123*'
                    bat 'cf create-org sampleapp'
                    //bat 'cf push'
                }
            }

        }

    }

}
