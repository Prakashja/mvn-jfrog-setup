pipeline {  
    agent any  
    tools {
        maven 'maven3.6'
        jdk 'java8'
    }
    parameters {
  string defaultValue: 'dev', description: '', name: 'environment', trim: false
}

    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }
     
     stage ('clone') {
            steps {
                git credentialsId: 'node1', url: 'https://github.com/Prakashja/mvn-jfrog-setup.git'
            }

        }

        stage ('Build') {
            steps {
                sh 'mvn clean package' 
            }
        }
      stage ('Build-status') {
            steps {
                sh 'echo build success' 
            }
    }
       stage ('deploy') { 
           steps {
            sh 'touch mydeploy.txt'
               echo "${environment}"
           }
       }
       stage ('clean workspace') { 
           steps {
            cleanWs()
           }
       }
}
}
