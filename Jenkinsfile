pipeline {
agent none


    stages {

        stage('Clone job 1') {
			agent {
				label 'master'
			}
            steps {
				git url: 'https://github.com/werdervg/job1.git'
            }
        }
        stage('Building..') {
			agent {
				label 'master'
			}
            steps {
                sh 'echo "Start building.."'
				sh 'chmod +x job1.sh'
				sh './job1.sh'
            }
        }
        stage('Clone job 2') {
			agent {
				label 'slave'
			}
            steps {
				git url: 'https://github.com/werdervg/job2.git'
            }
        }
        stage('Building..') {
			agent {
				label 'slave'
			}
            steps {
                sh 'echo "Start building.."'
				sh 'chmod +x job2.sh'
				sh './job2.sh'
            }
        }
    }
}


