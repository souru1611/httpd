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
				sh "docker run -d httpd "
				sh "docker run -itdp 80:80 --name server httpd "
				sh "cp /mnt/data-0/index.html /usr/local/apache2/htdocs "
				
			}				

		}

	}
}
