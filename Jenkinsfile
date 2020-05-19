pipeline {
    
    agent any
node('master') {
    stage('GetNodeName') {
    def node_name = "${NODE_NAME}"
    echo "The Node Name is: ${node_name}"
    }
}
    
    tools {
        maven 'maven3.6.3'
        jdk 'java8'
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
                git 'https://github.com/Prakashja/mvn-jfrog-setup.git'
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
           }
       }
       stage ('clean workspace') { 
           steps {
            cleanWs()
           }
       }
}
}
