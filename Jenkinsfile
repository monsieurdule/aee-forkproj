pipeline {

    agent {
        label 'vm'
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
                junit(testResults: '/home/jenkins/agent/workspace/forkproj-jenkins-pipeline/target/surefire-reports/*.xml', allowEmptyResults : true)
            }
        }
    }

        stage("run") {

            steps{
                sh "mvn exec:java"
            }
        }

    }
    
}
