pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                buildResult = """${bat(
                    returnStdout: true,
                    script: 'echo "clang"'
                )}"""
                withMaven {
                    bat "mvn clean verify"
                }
            }
        }
        stage("Test"){
            steps{
                recordIssues tool: java(), ignoreQualityGate: false, ignoreFailedBuilds: true
                junit allowEmptyResults: true, testResults: "${WORKSPACE}/test-results/*.xml"
            }
        }
        stage("Deploy"){
            steps{
                echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
                echo "Build result: ${buildResult}"
            }
        }
    }
}