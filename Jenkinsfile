pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'docker build -t flask-app:v1 .'
            }
        }
		stage ('Deploy') {
		    steps {
			    bat 'docker run -d -p 5000:5000 flask-app:v1'
			}
		}
    }
}