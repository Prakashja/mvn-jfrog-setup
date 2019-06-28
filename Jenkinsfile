pipeline {
agent any
tools{
maven 'maven'
jdk 'java'
}
 
stages {
stage ("initialize") {
steps {
sh '''
echo "PATH = ${PATH}"
echo "M2_HOME = ${M2_HOME}"
'''
}
}


stage ('Build project') {
steps {
 
git 'https://github.com/Prakashja/mvn-jfrog-setup.git'
sh 'mvn clean verify'
 

}
}
}
}
