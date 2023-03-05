pipeline{
	agent{
		label{
			label "built-in"
		}
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
				sh 'ansible all -m shell -a "sudo yum install httpd -y" -u ansible --become-user root'
			}
		}
		stage("deploying index.html to httpd"){
			steps{
				sh 'ansible all -bm copy "src=index.html dest=/var/www/html/'
				 sh 'ansible all -bm service "name=httpd status=restarted" '
			}
		}
	}

	
}
