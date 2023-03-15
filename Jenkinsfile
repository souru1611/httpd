pipeline {
	agent {
		label {
			label "built-in" 
			customWorkspace "/mnt/data-2 " 
		}	
	}

	stages {

		stage ("stage-1") {

			steps {  
				 sh "docker run -itdp 8081:80 --name server-2 httpd "
				 sh "cp /mnt/data-2/index.html /usr/local/apache2/htdocs "
					

			}				

		}

	}
}
