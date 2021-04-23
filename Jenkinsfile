pipeline {
    agent none
    stages{
        stage('Build') {
            steps {
                agent { docker 'maven:3.5-alpine'}
                sh 'mvn -B -DskipTest clen package'
            }
        }
    }
}