pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                script {
                    // Checkout the 'main' branch from the specified GitHub repository
                    checkout([$class: 'GitSCM', 
                        branches: [[name: '*/main']],
                        userRemoteConfigs: [[url: 'https://github.com/SwiftSoft-Bahadur/maven-web-app.git']]
                    ])
                }
            }
        }
         stage('Unit testing') {
            steps {
                script {
                    // Use the configured Maven installation
                    def mavenHome = tool name: 'Maven-3.9.4', type: 'Tool'
                    sh "${mavenHome}/bin/mvn test"
                }
            }
        }
    }
}
