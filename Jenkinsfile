pipeline {
		agent {
		node {
			label ('built-in')
		}
		}

		stages {
		stage ('install-git-docker') {
		steps {
	
			sh "yum install docker -y"
			sh "systemctl start docker"
			sh "chmod -R 777 /mnt"
		
	}
	}
			
		stage ('install-docker-compose') {
		steps {
	
			sh "curl -SL https://github.com/docker/compose/releases/download/v2.11.0/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose"
			sh "sudo chmod +x /usr/local/bin/docker-compose"
			sh "sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose"
			sh "sudo chmod +x /usr/bin/docker-compose"
		
	}
	}	
			
			
		stage ('gitrepo-copy') {
		steps {
		dir ('/mnt/repo') {
			sh "rm -rf *"
			sh "git clone https://github.com/ronitunale/docker3.git"
			sh "chmod -R 777 /mnt"
			sh "cp /mnt/repo/docker3/docker-compose.yaml /mnt"
			sh "mkdir wars"
			sh "cp /mnt/repo/docker3/gameoflife.war /mnt/wars"
			
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
