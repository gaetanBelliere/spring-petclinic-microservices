pipeline { 
    agent any
    tools { 
        maven 'maven' 
    }  
    stages {
        stage ('Artifactory configuration and deployment') {
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
                rtMavenRun (
                    pom: 'pom.xml',
                    goals: 'clean install',
                    // Maven options.
                    opts: '',
                    resolverId: 'MAVEN_RESOLVER',
                    deployerId: 'MAVEN_DEPLOYER'
                )
            }
        }
        
    }
}
