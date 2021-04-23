pipeline { 
    agent any
    tools { 
        maven 'maven' 
    }  
    stages { 
        stage('Build') { 
            steps { 
               echo 'This is a minimal pipeline.'
               sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}