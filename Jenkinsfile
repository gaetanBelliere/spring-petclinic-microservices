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
        stage ('Upload') {
            steps {
                rtUpload (
                    buildName: JOB_NAME,
                    buildNumber: BUILD_NUMBER,
                    serverId: SERVER_ID, // Obtain an Artifactory server instance, defined in Jenkins --> Manage:
                    spec: '''{
                              "files": [
                                 {
                                  "pattern": "$WORKSPACE/Demo-Artifactory/Artifact_*",
                                  "target": "result/",
                                  "recursive": "false"
                                } 
                             ]
                        }'''    
                )
            }
        }
    }
}
