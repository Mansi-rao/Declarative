pipeline{
    agent any
    tools{
        jdk 'jdk11'
        maven 'maven3'
    }
    environment{
        PRAGRA_INSTRUCTOR='Mansi Rao'
    }
    options{
        buildDiscarder(logRotator(numToKeepStr: '3'))
    }
    parameters { 
        choice(name: 'DEPLOY_ENV', choices: ['UAT1', 'UAT2', 'UAT3'], description: 'Select the envirnoment you want') 
    }
    stages{
        
        stage('Compile')
        {
            steps{
                sh 'mvn compile'
            }
        }

        stage('Test')
        {
            steps{
                sh 'mvn test'
            }
        }

        stage('Package')
        {
            steps{
                sh 'mvn package'
            }
        }
    }
}