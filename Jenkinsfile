pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "mvn"
    }

    stages {
        stage('Build') {
            steps {
             
                // Run Maven on a Unix agent.
                sh "mvn  clean package"
        }
    }
    stage('Test')
    {
        steps{
            echo "Testing start App testing"
        }
    }
    stage('email notification'){
        steps{
            mail bcc: '', body: 'sample pipeline', cc: '', from: '', replyTo: '', subject: '', to: 'coolgirl.buddha@gmail.com'
        }
    }
    stage('git checkout'){
        steps{
            git 'https://github.com/prasannabu/docker-java.git'
        }
    }
    stage('email job notification'){
        steps{
           mail bcc: '', body: '"Status of  \'${env.JOB_NAME} [${env.BUILD_NUMBER}]\'"', cc: '', from: '', replyTo: '', subject: '"Jobs status \'${env.JOB_NAME} [${env.BUILD_NUMBER}]\'"', to: 'coolgirl.buddha@gmail.com' 
        }
    }
    stage('git pull'){
        steps{
            git 'https://github.com/prasannabu/docker-java.git'
        }
    }
}
}
