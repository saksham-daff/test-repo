pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
		stage('Tester') {
            steps {
                sh 'echo "Awesome"'
                sh '''
                    echo "Multiline shell steps works too \n
                    lets do somethings...."
                '''
		    sh 'echo "No Fail!!!"'
            }
        }
	}
	post {
        always {
            echo 'This will always run'
	    emailext body: 'Sent using Jenkinsfile...😎', subject: 'Jenkinsfile pipeline testmail', to: 'saksham.gupta@daffodilsw.com,shashank.g@daffodilsw.com'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
