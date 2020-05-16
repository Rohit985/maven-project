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
    stage ('SCM test')
    {
        steps {
            withMaven(maven: 'Local_Maven') {
            sh 'maven test'        
			}
              }
    }
}
}
