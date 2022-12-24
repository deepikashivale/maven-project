pipeline{
agent any
stages{

stage ('Stage1: SCM Checkout')             //download the code
{steps{git branch: 'master' , url: 'https://github.com/deepikashivale/maven-project.git' }}    //if no branch defined then by default it will download from master

stage ('Stage2: Test the Code')
{steps{withMaven(globalMavenSettingsConfig: '--- Use system default settings or file path ---', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '--- Use system default settings or file path ---') {
    {sh 'mvn test'}
}}
}
}
