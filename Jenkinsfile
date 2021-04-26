pipeline { 
    agent any
    tools { 
        maven 'maven' 
    }  
    stages {
        stage ('Artifactory configuration') {
            steps {
                rtMavenDeployer (
                    id: "MAVEN_DEPLOYER",
                    serverId: "gaet.jfrog.io",
                    releaseRepo: "libs-release-local",
                    snapshotRepo: "libs-snapshot-local"
                )
                rtMavenResolver (
                    id: "MAVEN_RESOLVER",
                    serverId: "gaet.jfrog.io",
                    releaseRepo: "libs-release",
                    snapshotRepo: "libs-snapshot"
                )
                rtMavenRun (
                    pom: "pom.xml",
                    goals: 'package',
                    // Maven options.
                    opts: '',
                    resolverId: 'MAVEN_RESOLVER',
                    deployerId: 'MAVEN_DEPLOYER'
                )
            }
        }
        
    }
}
