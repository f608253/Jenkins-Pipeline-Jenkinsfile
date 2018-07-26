pipeline {
    agent any 
    stages {
        stage ('Compile Stage'){
            sh "'${M2_HOME}/bin/mvn' -Dmaven.test.failure.ignore clean compile"
           } 
        }
}
