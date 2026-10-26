pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Telemetry Build') {
            steps {
                echo 'Building Fleet Telemetry Service'
                sh 'test -f telemetry.conf'
                sh 'cat telemetry.conf'
            }
        }

        stage('Deploy Artifact') {
            steps {
                archiveArtifacts artifacts: 'telemetry.conf',
                                 fingerprint: true
            }
        }
    }
}