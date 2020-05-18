pipeline
{
    agent any
    stages
{
    stage ('SCM Repository')
    {
        steps {
            git branch: 'master', url: 'https://github.com/Rohit985/maven-project.git'
        }
    }
    
    stage ('SCM Compile')
    {
        steps {
            withMaven(maven: 'Local_Maven') {
            sh 'mvn compile'        
			}
              }
    }
	stage ('SCM Test')
    {
        steps {
            withMaven(maven: 'Local_Maven') {
            sh 'mvn test'        
			}
              }
    }
	stage ('SCM pakcgae')
    {
        steps {
            withMaven(maven: 'Local_Maven') {
            sh 'mvn package'        
			}
              }
    }
	stage ('SCM deploy into Tomcat server')
    {
        steps {
            sshagent (credentials: ['tomcat-ssh-id1']) {
	    sh 'scp -o StrictHostKeyChecking=no **/target/*.war ec2-user@172.31.18.5:var/lib/tomcat/webapps'
                                                      }
              }
    }	
}
}


