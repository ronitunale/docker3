pipeline {
		agent {
		node {
			label ('172.31.38.200')
		}
		}

		stages {
		stage ('install-git-docker') {
		steps {
	
			sh "sudo yum install docker -y"
			sh "sudo systemctl start docker"
			sh "sudo chmod -R 777 /mnt"
		
	}
	}
		
		stage ('gitrepo-copy') {
		steps {
		dir ('/mnt/repo') {
			sh "sudo git clone https://github.com/ronitunale/docker3.git"
			sh "sudo chmod -R 777 /mnt"
			sh "sudo cp /mnt/repo/docker3/docker-compose.yaml /mnt"
			sh "sudo mkdir wars"
			sh "sudo cp /mnt/repo/docker3/gameoflife.war /mnt/wars"
			
	}
	}
	}
	
		stage ('Deploy-tomcat-on-docker') {
		steps {
		dir ('/mnt') {
			sh "docker-compose up -d"
				
	}
	}
	}
		
			
	
	}

}
