pipeline {

    agent any

    tools {
        maven-forkproj
        jdk 'jdk11'
    }

    stages {
        stage("compile") {
            steps {
                sh "mvn compile"
            }
        }

        stage("test") {

            steps{
                sh "mvn test"
            }
        }

        stage("run") {

            steps{
                sh "mvn exec:java"
            }
        }
    }
}
