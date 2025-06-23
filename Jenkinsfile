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
				sh 'docker run -d --name html-app-container -p 8000:80 docker-image'
			}
		}
		stage('Can Jenkins talk to Docker?') {
            		steps {
                		sh 'whoami'
                		sh 'docker ps'
            		}
		}
}
