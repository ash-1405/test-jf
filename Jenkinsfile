pipeline {
		
		agent {
				label {
						label "built-in"
						customWorkspace "/mnt/test-tf"
				}
		}
		
		stages {
				stage ('install-httpd') {
							
							steps {
									sh "yum install httpd -y"
							}
				}
				
				stage ('start-httpd') {
							
							steps {
									sh "sudo systemctl start httpd"
							}
				}
				
				stage ('deploy') {
							
							steps {
									sh "sudo cp index.html /var/www/html"
									sh "sudo cp dev.html /var/www/html"
									sh "sudo chmod -R 777 /var/www/html"
							}
				}
		}
}
