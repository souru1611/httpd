pipeline {
	agent {
		label {
			label "built-in" 
			customWorkspace "/mnt/data-3" 
		}	
	}

	stages {

		stage ("stage-1") {

			steps {
				sh "yum install docker -y" 
				sh "systemctl start docker"
				sh "docker rmi -f httpd "
				sh "docker run -d httpd "
				sh "docker run -itdp 8088:80 --name server-8 httpd "
				sh "docker cp /mnt/data-3/index.html server-8:/usr/local/apache2/htdocs "
				sh "docker exec server-8 chmod -R 777 /usr/local/apache2/htdocs/index.html "
			}				

		}

	}
}
