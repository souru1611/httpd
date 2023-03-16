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
				sh "docker run -itdp 8087:80 --name server-7 httpd "
				sh "docker cp /mnt/data-1/index.html server-7:/usr/local/apache2/htdocs "
				sh "docker exec server-7 chmod -R 777 /usr/local/apache2/htdocs/index.html "
			}				

		}

	}
}
