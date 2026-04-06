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
			echo "=== DEBUG START ==="
			pwd
			ls -l

			pkill node || true

			nohup node server.js > app.log 2>&1 &

			sleep 2

			echo  "=== AFTER START ==="
			ps aux | grep node
		
			echo "=== LOG CONTENT ==="
			cat app.log || echo "No log file"
			'''			 
}
		}
	}
}
