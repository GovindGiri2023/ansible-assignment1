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
				sh 'ansible 23Q1 -m yum -a "name=httpd state=present" '
			}
		}
		stage("deploying index.html to httpd"){
			steps{
				sh 'ansible 23Q1 -m copy -a "src=index.html dest=/var/www/html/ mode=0777" --become'
				 sh 'ansible 23Q1 -m service -a "name=httpd state=restarted" --become '
			}
		}
	}

	
}
