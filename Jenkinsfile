pipeline {
agent any
stages {
        stage('build') {
            steps {
                echo 'Building..'
				sh 'pwd; chmod 777 build deploy test; ./build'		
            }
        }
        stage('deploy') {
            steps {
                echo 'Deploying to TEST environment..'
				sh 'chmod 777 build deploy test; ./deploy'
            }
        }
        stage('test') {
            steps {
                echo 'Testing....'
				sh 'chmod 777 build deploy test; ./test'
					}
				}
    }
}
