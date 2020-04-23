pipeline {
    options {
        timeout(time: 45, unit: 'MINUTES')
    }
    agent any
    environment {
        DOCKER_BUILD_TAG = sh(returnStdout: true, script: "git describe --tags")
    }
    stages {
        stage('Set build tag') {
            steps {
                script {
                    currentBuild.displayName = "${DOCKER_BUILD_TAG}"
                }
            }
        }
        stage('Print file contents') {
            steps {
                    sh "ls -l; pwd; cat where-am-i"
            }
        }
    }
}
