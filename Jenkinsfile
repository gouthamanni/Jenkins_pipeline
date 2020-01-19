pipeline {
agent none
stages {
        stage('build') {
		parallel{
		agent { label 'master' }
            steps {
                echo 'Building..'
				sh 'pwd; chmod 777 build deploy test; ./build'	
	    }
            }
        }
        stage('deploy') {
		parallel{
		agent { label 'slave' }
            steps {
                echo 'Deploying to TEST environment..'
				sh 'chmod 777 build deploy test; ./deploy'
	    }
            }
        }
        stage('test') {
		parallel {
		agent { label 'slave' }
            steps {
                echo 'Testing....'
				sh 'chmod 777 build deploy test; ./test'
					}
				}
	}
    }
}
