
pipeline {
      agent any
      stages {
         stage ('Build') {
          steps {
             sh '''cd $WORKSPACE
                   docker build -t devops-react:v${BUILD_NUMBER} .'''
             }
           }
           stage('push ECR'){
            steps {
                sh '''aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 767397709049.dkr.ecr.us-east-1.amazonaws.com
                         docker tag devops-react:v${BUILD_NUMBER} 767397709049.dkr.ecr.us-east-1.amazonaws.com/devops19-reactjs:v${BUILD_NUMBER}
                           docker push 767397709049.dkr.ecr.us-east-1.amazonaws.com/devops19-reactjs:v${BUILD_NUMBER}
           		    
		   
       '''
            }
          }

          }
        }
