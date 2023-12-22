pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                bat 'docker build -t flask-app:v1 .'
            }
        }
		
		stage ('Pushing the Image into Dockerhub') {
		    steps {
			    bat "docker login -u sid2104 -p BaPP4082#@Y docker.io"
				bat "docker tag flask-app:v1 sid2104/dockerhub:flaskapp"
				bat "docker push sid2104/dockerhub:flaskapp"
			}
		}

        stage ('Deploy') {
		    steps {
			    bat 'docker run -d -p 5000:5000 flask-app:v1'
			}
		}		
			
    }
}