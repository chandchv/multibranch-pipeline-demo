pipeline {

    agent {
        node {
            label 'master'
        }
    }

    options {
        buildDiscarder logRotator( 
                    daysToKeepStr: '16', 
                    numToKeepStr: '10'
            )
    }

    stages {
        
        stage('Cleanup Workspace') {
            steps {
                script {
                cleanWs()
               // sh """
                echo "Cleaned Up Workspace For Project"
              //  """
                }
            }
        }

        stage('Code Checkout') {
            steps {
                checkout([
                    $class: 'GitSCM', 
                    branches: [[name: '*/main']], 
                    userRemoteConfigs: [[url: 'https://github.com/spring-projects/spring-petclinic.git']]
                ])
            }
        }

        stage(' Unit Testing') {
            steps {
                script {
               // sh """
                echo "Running Unit Tests"
               // """
                }
            }
        }

        stage('Code Analysis') {
            steps {
                script {
               // sh """
                echo "Running Code Analysis"
               // """
                }
            }
        }

        stage('Build Deploy Code') {
            when {
                branch 'develop'
            }
            steps {
                script {
               // sh """
                echo "Building Artifact"
              //  """

              //  sh """
                echo "Deploying Code"
              //  """
                }
            }
        }

    }   
}
