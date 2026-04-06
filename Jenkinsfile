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
			cd /home/ubuntu/node-jenkins-app

			pkill node || true

			nohup node server.js > app.log 2>&1 &

			sleep 2

		
			ps aux | grep node
		
		
			'''			 
}
		}
	}
}
