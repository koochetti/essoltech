pipeline{
   agent any
    stages 
	{
		stage("docker build"){
			steps{
				sh """
					docker build -t koochetti/essoltech .
				"""
			}
		}
		stage("push to DTR"){
			steps{
			withCredentials([usernamePassword(credentialsId: 'dp', usernameVariable: 'USER', passwordVariable: 'PASSWORD')])
			{
				sh """
				     sudo docker login --username $USER --password $PASSWORD
			             sudo docker push koochetti/essoltech
				"""
			}
		
		   }
              }
		
	}
}
