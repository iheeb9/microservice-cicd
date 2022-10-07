properties([pipelineTriggers([githubPush()])])
pipeline {
    agent any 
     tools { 
        maven 'M2_HOME' 
        
    }
    stages {
        stage('git clone') {
            steps {
               git branch: 'main', url: 'https://github.com/iheeb9/microservice-cicd.git'
        
            }
        }
        stage('clean package') {
            steps {
             echo "M2_HOME = ${M2_HOME}"
             sh 'mvn clean install'
        
        
            }
        }
    }
    
    post{
        always{
        
        emailext body: 'jenkins', subject: 'jenkins', to: 'iheb.youssef@esprit.tn'
        }
        
    }
        
        
}
