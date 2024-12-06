pipeline {
    agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }
    
    environment {
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'admin123'
        NEXUSIP = '172.31.28.132'
        NEXUSPORT = '8081'
    }

    stages {
        stage('Build') {
            steps {
                sh '''
                    mvn -s settings.xml -DskipTests install \
                        -Denv.NEXUS_USER=$NEXUS_USER \
                        -Denv.NEXUS_PASS=$NEXUS_PASS \
                        -Denv.NEXUSIP=$NEXUSIP \
                        -Denv.NEXUSPORT=$NEXUSPORT
                '''
            }
        }
    }
}
