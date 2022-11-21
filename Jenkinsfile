pipeline {

    agent {
        label 'vm'
    }

    post {
            always {
                junit(testResults: 'forkproj-jenkins-pipeline/target/surefire-reports/*.xml', allowEmptyResults : true)
            }
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
