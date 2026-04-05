pipeline {
	agent {
		docker { image 'node:18-alpine' }
	}


	stages {
		stage('Install') {
		steps {
			sh 'npm install'
		     }
		}


	stage('Test') {
		steps {
			sh 'npm test'
			}
		}


	stage('Run App') {
		steps {
			sh '''
			apk add --no-cache curl
			node server.js &
			sleep 5
			curl localhost:3000
			'''			 
}
		}
	}
}
