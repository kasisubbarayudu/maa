pipeline {
    agent { label 'Build-Node' } 
    options {
        buildDiscarder(logRotator(numToKeepStr: '10'))
    }
    stages {
        stage ('Lint') {
            when { anyOf { branch 'dev*'; branch 'master'; branch 'PR*'; branch 'feature*' } }
            steps {
                script {
                    echo "This is test stage"
                }
            }
        } 
        stage ('Unit') {
            when { anyOf { branch 'dev*'; branch 'master'; branch 'PR*' } }
            steps {
                script {
                    echo "This is Unit stage"
                }
            }
        }
        stage ('Build') {
            when { branch 'master' }
            steps {
                script {
                    echo "This is build stage"
                }
            }
        } 
         
    }
}