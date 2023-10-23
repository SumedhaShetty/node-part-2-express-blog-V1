pipeline {
    agent any

    tools {nodejs "node"}

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh '''
                #!/bin/bash
                rm -rf *.tar.gz
                npm install
                tar czf node-build.tar.gz blog.js package.json pm2config.json
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing the application...'
                sh 'npm run test'
            }
        }
    }
}
