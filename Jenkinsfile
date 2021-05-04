pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                withMaven {
                    bat "mvn clean verify"
                }
                echo "This is a test for git"
            }
        }
        stage("Test"){
            steps{
                recordIssues tool: java(), ignoreQualityGate: false, ignoreFailedBuilds: true
            }
        }
    }
}