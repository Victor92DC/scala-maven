// Instead of annotating an unnecessary import statement, the symbol _ is annotated, according to the annotation pattern.
@Library('adop-pluggable-scm-jenkinsfile') _

def repoName = "scala-maven-template-master"
def regRepo = "adop-cartridge-scala-regression-tests"

pipeline {
    agent { label 'java8' }
    
    stages{
        stage("Reference Application Build"){
            steps{
                echo 'Compiling...'
                deleteDir()
                checkout scm
                withMaven(maven: 'ADOP Maven') {
                    sh 'mvn clean install'   //sustitye aqui el comando maven q quieras
                }
            }
            stage("Reference Application Unit Tests"){
                steps{
                    echo 'Testing...'
                    withMaven(maven: 'ADOP Maven') {
                        sh "mvn test"
                    }   
                }  
            }
         }
     }
}
