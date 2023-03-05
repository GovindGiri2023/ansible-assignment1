pipeline{
	agent{
		label{
			label "built-in"
		}
	}
	tools{
	   ansible "ansible"
	}

	stages{
		stage("clean workspace"){
			steps{
				cleanWs()
			}
		}
		stage("checkout from scm"){
			steps{
				checkout scm
			}
		}
		stage("installin web server on ansible hosts"){
			steps{
				sh 'ansible -a "sudo yum install httpd -y " '
			}
		}
	}

	
}
