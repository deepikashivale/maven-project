pipeline{
agent any
stages{

stage ('Stage1: SCM Checkout')             //download the code
{steps{git branch: 'master' , url: 'https://github.com/deepikashivale/maven-project.git' }}    //if no branch defined then by default it will download from master

//stage ('Stage2: Build the Code')
//{steps{sh 'mvn clean package'}}

//stage ('Stage3: Deploy the Code')
//{steps{



}
}
