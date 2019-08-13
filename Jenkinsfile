#!/usr/bin/env groovy
pipeline {
    agent {
        label "maven"
    }
    options {
        timestamps()
    }
    stages {
        stage('Test') {
            steps {
                sh 'mvn -B clean test'
            }
            post {
                always {
                    junit(keepLongStdio: true, testResults: 'target/surefire-reports/TEST-*.xml')
                }
            }
        }
    }
}
