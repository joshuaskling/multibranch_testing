pipeline {
    agent any
    stages {
        stage("build") {
            steps {
                withMaven {
                    mvn clean verify
                }
            }
        }
    }
}