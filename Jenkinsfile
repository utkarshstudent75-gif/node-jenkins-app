pipeline {
	agent {
		docker { image 'node:18-alpine'
			 args '-u root'			 }
					
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
			echo "current directory:"
			pwd

			echo "Files in directory:"
			ls -l

			pkill node || true

			nohup node server.js > app.log 2>&1 &
			'''			 
}
		}
	}
}
