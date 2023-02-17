pipeline {
	agent any
	environment {
		NEW_VERSION = '1.0.0'
	}
	stages {
		stage("build") {
			steps {
				echo 'building the applicaiton...'
				echo "building version ${NEW_VERSION}"
			}
		}
		stage("test") {
			steps {
				echo 'testing the applicaiton...'
			}
		}
		stage("deploy") {
			steps {
				echo 'deploying the applicaiton...'
				withCredentials([[$class: 'UsernamePasswordMultiBinding',
					credentialsId: 'admin_user_credentials', 
					usernameVariable: 'USER', 
					passwordVariable: 'PWD'
				]]) {
					sh 'printf ${USER}'
				}
			}
		}
	}
}