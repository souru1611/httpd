pipeline {
	agent {
		label {
			label "built-in" 
			customWorkspace "/mnt/data-0" 
		}	
	}

	stages {

		stage ("stage-1") {

			steps {
				sh "yum install docker -y" 
				sh "systemctl start docker"
				sh "docker rmi -f httpd "
				sh "docker run -d httpd "
				sh "docker run -itdp 8089:80 --name server-9 httpd "
				sh "docker cp /mnt/data-0/index.html server-9:/usr/local/apache2/htdocs "
				
			}				

		}

	}
}
