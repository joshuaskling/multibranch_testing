pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                withMaven {
                    bat "mvn clean verify"
                }
            }
        }
        stage("Test"){
            steps{
                recordIssues tool: java(), ignoreQualityGate: false, ignoreFailedBuilds: true
                junit 'test-results.xml'
            }
        }
    }
}