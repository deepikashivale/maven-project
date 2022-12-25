pipeline{
agent any
stages{

stage ('Stage1: SCM Checkout')             //download the code
{steps{git branch: 'master' , url: 'https://github.com/deepikashivale/maven-project.git' }}    //if no branch defined then by default it will download from master

stage ('Stage2: Execute Unit Test Framework')
{steps{withMaven(globalMavenSettingsConfig: 'fcee6e46-273c-4d32-b3ad-288e1b70f59a', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: 'e60d62d0-dc77-49d2-9393-fea1c9fb6a8d') 
{sh 'mvn test'}
}}

stage ('Stage3: Create Deployable Package')
{steps{withMaven(globalMavenSettingsConfig: 'fcee6e46-273c-4d32-b3ad-288e1b70f59a', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: 'e60d62d0-dc77-49d2-9393-fea1c9fb6a8d') 
{sh 'mvn clean package'}
}}

stage ('Stage4: Deploy Package to Dev Environment')
{steps{ sshagent(['a6ac4d02-766a-49f8-8025-b1aa2a249ef6']) {
   sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@13.127.169.162:/var/lib/tomcat/webapps' 
} }}

}
}
