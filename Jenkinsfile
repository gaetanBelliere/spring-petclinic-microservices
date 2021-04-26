pipeline { 
    agent any
    tools { 
        maven 'maven' 
    }  
    stages { 
        stage('Build') { 
            steps { 
               sh 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') { 
            steps {
                sh 'mvn test' 
            }
        }
        stage('Integration Tests') {
            steps {
                sh 'mvn -B integration-test'
            }
            post {
                always {
                    junit '**/target/failsafe-reports/*.xml'
                }
            }    
        }
    }
}