pipeline {
    agent none 
    stages {
        stage('BUILD') {
            agent any
            steps {
                sh '''
                    #!/bin/bash 
                    pwd 
                    ls
                    echo "This is a BUILD stage"
                    sleep 5
                '''  
            }
        }
        stage('DEPLOY') {
            agent { label 'cnode' } 
            steps {
                echo "This is a DEPLOY stage"
                sh 'sleep 5'
            }
        }
        stage('TESTING') {
            parallel {
                stage('TESTING1') {
                    agent { label 'jnode' } 
                    steps {
                        sh 'echo "This is a TESTING1 stage"'
                        sh 'sleep 5'
                    }
                }
                stage('TESTING2') {
                    agent { label 'master' } 
                    steps {
                        sh '''
                            echo "This is a TESTING2 stage"
                            sleep 5
                        '''
                    }
                }
                
        }    
    }
}
