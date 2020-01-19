pipeline {
agent none
stages {
        stage('build') {
		agent { label 'master' }
            steps {
                echo 'Building..'
				sh 'pwd; chmod 777 build deploy test; ./build'		
            }
        }
        stage('deploy') {
		agent { label 'master' }
            steps {
                echo 'Deploying to TEST environment..'
				sh 'chmod 777 build deploy test; ./deploy'
            }
        }
        stage('test') {
		agent { label 'master' }
            steps {
                echo 'Testing....'
				sh 'chmod 777 build deploy test; ./test'
					}
				}
    }
}
