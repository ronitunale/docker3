pipeline {
		agent {
		node {
			label ('built-in')
		}
		}

		stages {
		stage ('install-java-git-docker') {
		steps {
			sh "sudo yum install java-1.8.0-openjdk-devel.x86_64 -y"
			sh "sudo yum insatll git -y"
			sh "sudo yum install docker -y"
			sh "sudo systemctl start docker"
			sh "sudo chmod -R 777 /mnt"
		
	}
	}
		stage ('install-docker-compose') {
		steps {
			sh "sudo curl -SL https://github.com/docker/compose/releases/download/v2.11.0/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose"
			sh "sudo chmod +x /usr/local/bin/docker-compose"
			sh "sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose"
			sh "sudo chmod +x /usr/bin/docker-compose"	
	}
	}
	
		stage ('gitrepo-copy') {
		steps {
		dir ('/mnt/SC') {
			sh "git clone "
			sh "sudo chmod -R 777 /mnt"
			
	}
	}
	}
	
	
	}

}
