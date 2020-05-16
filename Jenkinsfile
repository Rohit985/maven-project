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
    stage ('SCM compile')
    {
        steps {
            withMaven(maven: 'Local_Maven') {
            sh 'mvn compile'        
			}
              }
    }
    stage ('SCM test')
    {
        steps {
            withMaven(maven: 'Local_Maven') {
            sh 'mvn test'        
			}
              }
    }
    stage ('SCM package')
    {
        steps {
            withMaven(maven: 'Local_Maven') {
            sh 'mvn package'        
			}
              }
    }		
}
}
