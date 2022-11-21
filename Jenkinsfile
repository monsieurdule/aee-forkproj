pipeline {

    agent any

    stages {
        stage("compile") {
            steps {
                mvn compile
            }
        }

        stage("test") {
            steps{
                mvn test
            }
        }

        stage("run"){
            steps{
                mvn exec:java
            }
        }
    }
}
