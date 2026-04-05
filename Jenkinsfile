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
			sh 'node server.js &'
			sleep 5
			sh 'curl localhost:3000'
			}
		}
	}
}
