pipeline {
    agent { label 'node1' }

    stages {
        stage ('compile') {
            steps {
                sh 'mvn compile'
            }
        }
        stage ('package') {
            steps {
                sh 'mvn package'
            }
        }
        stage ('SCA') {
            steps {
                sh ('/home/ubuntu/sonar-scanner-4.7.0.2747-linux/bin/sonar-scanner')
            }
        }
        stage ('deployment') {
            steps {
                sh ('cp ./target/addressbook-2.0.war /var/lib/tomcat9/webapps/addressbook.war')
            }
        }
        stage ('Email') {
            steps {
                sh (mail bcc: '', body: 'This is email to test my project', cc: 'kellymah21@gmail.com', from: '', replyTo: '', subject: 'Pipeline as a code test', to: 'stephanenoberts@gmail.com')
            }
        }
    }
}








