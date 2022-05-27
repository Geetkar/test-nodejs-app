pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'liquibase/liquibase'
                    // Run the container on the node specified at the top-level of the Pipeline, in the same workspace, rather than on a new node entirely:
                    reuseNode true
                }
            }
            steps {
                sh 'liquibase --version'
                sh 'liquibase init project'
                sh 'liquibase init start-h2'
            }
            
        } 
    }
}
