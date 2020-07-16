// node {
// 	stage('Build') {
// 		echo "Build"
// 	}
// 	stage('Test') {
// 		echo "Test"
// 	}
// }

pipeline {
	agent any
	// agent {docker { 
	// 	image 'maven:3-alpine'
    //     args '-u root'
	// 	}
	// }
	environment {
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
	}
	stages {
		stage('Build') {
			steps {
				//  sh 'mvn -B -DskipTests clean install'
				sh 'maven --version'
				sh 'docker version'
				echo "Build"
				echo "PATH - $PATH"
				echo "BUILD_NUMBER - $env.BUILD_NUMBER"

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