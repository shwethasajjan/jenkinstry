pipeline {
    agent { 'cnode' }
    stage{
       stage ('build') {
           steps {
           git branch: 'main', url: 'https://github.com/shwethasajjan/cfile.git'
           sh 'make'
           }
       
       }
       
       stage ('deploy') {
          steps {
          echo "this is a deploy stage"
          }
       
       }
       stage ('test') {
           steps {
           echo "this is a test stage"
           }
       }

    }
}
