pipeline { 
    agent any
    tools { 
        maven 'Maven 3.6.3' 
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