pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from your GitHub repository
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], userRemoteConfigs: [[url: 'https://github.com/youssef-Magic/jenkins.git']]])
            }
        }
	
	stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        
	stage('Send Email') {
            steps {
                // Send an email with the content of README.md
                emailext(
                    from: 'fareslaamloum@gmail.com',
                    subject: 'New Commit in GitHub Repository',
                    body: readFile('README.md'),
                    to: 'youssefcheour.5@gmail.com',
                    mimeType: 'text/plain'
                )
            }
        }
    }
}
