pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'main', credentialsId: 'GitHub', url: 'https://github.com/skattimath/SamplePHP.git'
                sh ''' echo "Checkout from GIT Done" '''
            }
        }
        stage('Deploy') {
			steps {
           // Push code to apache server
				sh '''#!/bin/bash
						pwd
						scp /var/lib/jenkins/workspace/cicd/inc/dbinfo.inc ec2-user@172.31.10.26:/var/www/inc/.
						scp /var/lib/jenkins/workspace/cicd/SamplePHP.php ec2-user@172.31.10.26:/var/www/html/.
						echo "Build Transfered Succesfully"
						'''
						
			}
        }
    }
}
