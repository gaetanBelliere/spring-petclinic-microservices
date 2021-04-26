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
        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
        stage('Deploy') {
            steps {
                sh 'mvn deploy'
            }
        }
    }
}