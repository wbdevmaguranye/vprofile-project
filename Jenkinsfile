pipeline {
    agent {
        label "any"
    }
    tools {
        maven 'MAVEN3' // Ensure "MAVEN3" is configured in Jenkins Global Tool Configuration
        jdk 'OracleJDK8' // Ensure "OracleJDK8" is configured in Jenkins Global Tool Configuration
    }
    environment {
        SNAP_REPO = 'vprofile-snapshot'
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'admin123'
        RELEASE_REPO = 'vprofile-release'
        CENTRAL_REPO = 'vprofile-maven-central'
        NEXUSIP = '172.31.28.132'
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'vpro-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
    }
    stages {
        stage("Build") {
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
        }
    }
}
