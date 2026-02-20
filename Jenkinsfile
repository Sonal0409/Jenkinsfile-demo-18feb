pipeline{
    // which server will the pipeline execute on
    // any = our current server (EC2 instance)
    agent {
        
     label 'linux_node'

    }
    tools{
        maven 'mymaven' // name of maven tool configured in Jenkins
    }
    stages{
        stage('Clone Repository'){
            steps{
              git  'https://github.com/Sonal0409/DevOpsCodeDemo.git'
            }
        }
        stage('Test the code'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Compile the code'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Review the code'){
            steps{
                sh 'mvn pmd:pmd'
            }
        }

        stage('Build the code'){
            steps{
                sh 'mvn package'
            }
        }
        
    }


}
