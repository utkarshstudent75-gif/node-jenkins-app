pipeline {
	agent {
		docker { image 'node:18-alpine' }
	}


	stage {
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
