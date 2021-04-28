pipeline {
    agent any
    stages {
        stage("build") {
            steps {
                withMaven {
                    bat "mvn clean verify"
                }
                echo "This is a test for git"
            }
        }
    }
}