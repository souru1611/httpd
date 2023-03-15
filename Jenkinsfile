pipeline {
	agent {
		label {
			label "built-in" 
			customWorkspace "/mnt/data-3 " 
		}	
	}

	stages {

		stage ("stage-1") {

			steps {
				sh "docker run -itdp 8082:80 --name server-3 httpd "	
				sh "cp /mnt/data-3/index.html /usr/local/apache2/htdocs "	

			}				

		}

	}
}
