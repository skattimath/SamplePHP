pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/skattimath/SamplePHP.git'
            }
        }
        stage('Deploy') {
			steps {
           // Push code to apache server
				sh '''#!/bin/bash
						pwd
						scp /home/ec2-user/trail-git/SamplePHP/inc/dbinfo.inc ec2-user@172.31.21.238:/var/www/inc/.
						scp /home/ec2-user/trail-git/SamplePHP/SamplePHP.php ec2-user@172.31.21.238:/var/www/html/.
						'''
			}
        }
    }
}
