pipeline {
	agent {
		label {
			label "built-in" 
			customWorkspace "/mnt/data-1" 
		}	
	}

	stages {

		stage ("stage-1") {

			steps {
				sh "yum install docker -y" 
				sh "systemctl start docker"
				sh "docker rmi -f httpd "
				sh "docker run -d httpd "
				sh "docker run -itdp 8091:80 --name server-11 httpd "
				sh "docker cp /mnt/data-1/index.html server-11:/usr/local/apache2/htdocs "
				sh "docker exec server-11 chmod -R 777 /usr/local/apache2/htdocs/index.html "
			}				

		}

	}
}
