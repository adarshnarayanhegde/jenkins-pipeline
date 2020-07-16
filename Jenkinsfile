// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// }

pipeline {
	// agent any
	agent {docker { 
		image 'maven:3-alpine'
        args '-u root'
		}
	}
	stages {
		stage('Build') {
			steps {
				 sh 'mvn -B -DskipTests clean install'
			}
		}

		stage('Test') {
			steps {
				echo "Test"
			}
		}

		stage('Integration Test') {
			steps {
				echo "Integration Test'"
			}
		}
	}

	post {
		always {
			echo "Always runs"
		}
		success {
			echo "Run on success"
		}
		failure {
			echo "run on failure"
		}
	}
}