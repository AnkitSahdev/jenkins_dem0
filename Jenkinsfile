pipeline{
    tools{
        jdk 'myjava'
        maven 'mymaven'
    }
    
    agent any
    
    stages{
        
        stage('CLone git repo')
        {
            steps{
                git 'https://github.com/Sonal0409/DevOpsCodeDemo.git'
            }
        }
        stage('Compile the source code'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Review the source code'){
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage('Testing'){
            steps{
                sh 'mvn test'
            }
            post{
                success{
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Package'){
            steps{
                sh 'mvn package'
            }
        }
    }
}
