pipeline{
    agent any
    stages{
        stage('checkout the code from github'){
            steps{
                 git url: 'https://github.com/Hemanthkl1987/my-new-banking-repo/'
                 echo 'github url checkout'
            }
        }
        stage('codecompile with hemanth'){
            steps{
                echo 'starting compiling'
                sh 'mvn compile'
            }
        }
        stage('codetesting with hemanth'){
            steps{
                sh 'mvn test'
            }
        }
        stage('qa with hemanth'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }
        }
        stage('package with hemanth'){
            steps{
                sh 'mvn package'
            }
        }
        stage('run dockerfile'){
          steps{
               sh 'docker build -t myimg .'
           }
         }
        stage('port expose'){
            steps{
                sh 'docker run -dt -p 8091:8091 --name c000 myimg'
            }
        }   
    }
}
