pipeline {
	agent any
	stages {
		stage('Upload to S3'){
			steps {
				sh 'echo "Hello World"'
				sh '''
					echo "Multiline shell steps work too"
					ls -lah
				'''
				dir('.'){
					sh 'current directory path'
					pwd();
					withAWS(region:'us-east-1',credentials:'aws-static'){
						def identity=awsIdentity();
						s3Upload(file:index.html,bucket:'devops-project3',path:'./index.html')

					}
				}
			}
		}
	}
}
