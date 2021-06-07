pipeline { 
    agent any
    tools { 
        maven 'maven' 
    }  
    stages {
        stage ('Artifactory configuration') {
            steps {
                rtMavenDeployer (
                    id: 'MAVEN_DEPLOYER',
                    serverId: 'gaet.jfrog.io',
                    releaseRepo: 'clinic-libs-release-local',
                    snapshotRepo: 'clinic-libs-snapshot-local'
                )
                rtMavenResolver (
                    id: 'MAVEN_RESOLVER',
                    serverId: 'gaet.jfrog.io',
                    releaseRepo: 'clinic-libs-release',
                    snapshotRepo: 'clinic-libs-snapshot'
                )
            }
        }
        stage ('Artifactory Maven Run') {
            steps {
                echo "Simulating Artifactory push" 
            }
        }
        
    }
}
