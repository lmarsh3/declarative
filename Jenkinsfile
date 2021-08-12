pipeline{
   //agent tells you where to declare the pipeline
    agent any
    tools{
        jdk 'jdk11'
        maven 'maven3'
    }
    environment {
        PRAGRA_STUDENT = 'Luke Marshall'
    }
    options{
        buildDiscarder(logRotator(numToKeepStr:'1'))
    }
    stages{
        stage('Compile'){
            steps {
                sh 'mvn compile'
            }

        stage('Test'){
            steps{
            sh 'mvn test'
            } 
        }

        stage ('Package'){
            steps{
            sh 'mvn package'
            }
        }

        stage('Archive Artificats'){
            steps{
                archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
    }
}