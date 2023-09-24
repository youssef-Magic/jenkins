pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your GitHub repository
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], userRemoteConfigs: [[url: '<repository_url>']]])
            }
        }
        stage('Send Email') {
            steps {
                // Send an email with the content of README.md
                emailext(
                    subject: 'New Commit in GitHub Repository',
                    body: readFile('README.md'),
                    to: 'youssefcheour.5@gmail.com',
                    mimeType: 'text/plain'
                )
            }
        }
    }
}
