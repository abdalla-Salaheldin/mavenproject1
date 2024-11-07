pipeline
{
agent any
stages
{
 stage('scm checkout')
 { steps { git branch: 'master', url: 'https://github.com/abdalla-Salaheldin/mavenproject1.git' }}

 stage('code compile')
 { steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MVN_HOME', mavenSettingsConfig: '', traceability: true)  {
	sh 'mvn compile'
 } }}

  stage('execute unit test framework')
 { steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MVN_HOME', mavenSettingsConfig: '', traceability: true)  {
	sh 'mvn test'
 } }}

   stage('code build')
 { steps { withMaven(globalMavenSettingsConfig: '', jdk: 'JDK_HOME', maven: 'MVN_HOME', mavenSettingsConfig: '', traceability: true)  {
	sh 'mvn clean -B -DskipTests package'
 } }}


 // stage('build docker image')
 // {steps { sh 'docker build -t pkw0301/devops:tomcat .' }}

}
}
