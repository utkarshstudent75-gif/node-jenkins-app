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
        echo "=== CURRENT DIR ==="
        pwd

        echo "=== FILES ==="
        ls -l

        echo "=== NODE VERSION ==="
        node -v

        echo "=== STARTING APP ==="
        pkill node || true

        node server.js
        '''
								 
}
		}
	}
}
