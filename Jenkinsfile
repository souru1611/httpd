pipeline {
	agent {
		label {
			label "built-in" 
			customWorkspace "/mnt/data-1 " 
		}	
	}

	stages {

		stage ("stage-1") {

			steps {
				 sh "docker run -itdp 8080:80 --name server-1 httpd "	
				 sh "cp /mnt/data-1/index.html /usr/local/apache2/htdocs "	

			}				

		}

	}
}
