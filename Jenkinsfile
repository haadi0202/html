pipeline{
agent any
	stages{
		stage("build"){
			steps{
				echo 'building...'
				sh 'docker build -t docker-image .'
			}
		}
		stage("deploy"){
			steps{
				echo 'deploying...'
				sh 'docker rm -f html-app-container || true'
				sh 'docker run -d --name html-app-container -p 8081:80 docker-image'
			}
		}
	}
}
