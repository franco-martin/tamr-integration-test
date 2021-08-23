pipeline {
    agent {
        docker { image 'hashicorp/terraform:0.15.5'
                 label 'docker'
                 args '-u root --entrypoint='
                }
    }
    stages {
        stage('Everytime') {
            steps {
                sh 'echo "this runs everytime"'
            }
        }
        stage('ON PR') {
            when { not { branch 'main' } }
            steps {
                sh 'echo "this runs on every PR"'
            }
        }
        stage('On tagged PR') {
            when { not { branch 'main' } }
            steps {
                sh 'echo "this runs on tagged PRs"'
                }
            }
        }
    }
}