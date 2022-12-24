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
{sh 'mvn clean packeage'}
}}



}
}
