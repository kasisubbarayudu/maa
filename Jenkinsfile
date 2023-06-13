pipeline {
    agent any 
    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    stages {
        stage ('Lint') {
            when { anyOf { branch 'dev*'; branch 'main'; branch 'PR*'; branch 'feature*' } }
            steps {
                script {
                    echo "This is test stage"
                    sh 'echo $env.BRANCH_NAME'
                }
            }
        } 
        stage ('Unit') {
            when { anyOf { branch 'dev*'; branch 'main'; branch 'PR*' } }
            steps {
                script {
                    echo "This is Unit stage"
                }
            }
        }
        stage ('Build') {
            when { branch 'main' }
            steps {
                script {
                    echo "This is build stage"
                }
            }
        } 
         
    }
} 
