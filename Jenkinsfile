pipeline
{
    agent any
    stages
{
    stage ('SCM Repository')
    {
        steps {
            git branch: 'brancjh', url: 'https://github.com/Rohit985/maven-project.git'
        }
    }
    
    stage ('SCM Compile')
    {
        steps {
            withMaven(maven: 'Local_Maven') {
            sh 'maven compile'        
			}
              }
    }
	stage ('SCM Test')
    {
        steps {
            withMaven(maven: 'Local_Maven') {
            sh 'maven test'        
			}
              }
    }
	stage ('SCM pakcgae')
    {
        steps {
            withMaven(maven: 'Local_Maven') {
            sh 'maven package'        
			}
    }
    }
}
}


