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
                    releaseRepo: 'petclinic',
                    snapshotRepo: 'petclinic'
                )
                rtMavenResolver (
                    id: 'MAVEN_RESOLVER',
                    serverId: 'gaet.jfrog.io',
                    releaseRepo: 'petclinic',
                    snapshotRepo: 'petclinic'
                )
                rtMavenRun (
                    pom: 'pom.xml',
                    goals: 'packaging',
                    // Maven options.
                    opts: '',
                    resolverId: 'MAVEN_RESOLVER',
                    deployerId: 'MAVEN_DEPLOYER'
                )
            }
        }
        
    }
}
