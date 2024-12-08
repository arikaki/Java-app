i@Library('my-shared-library') _

pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            when { expression { params.action == 'create' } }
            steps {
                gitCheckout(branch: "main", url: "https://github.com/arikaki/Java-app.git")
            }
        }
        stage('Unit Test maven') {
            when { expression { params.action == 'create' } }
            steps {
                script { mvnTest() }
            }
        }
        stage('Integration Test maven') {
            when { expression { params.action == 'create' } }
            steps {
                script { mvnIntegrationTest() }
            }
        }
    }
}

