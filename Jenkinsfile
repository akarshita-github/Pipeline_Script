pipeline {
     agent none
     stages {

     stage('Non-Parallel Stage') {
         agent {
                 label "master"
                }
         steps {
                 echo 'This stage will be executed first'
                 }
         }

         stage('Run Tests') {
             parallel {
                  stage('Test On Windows') {
                      agent {
                          label "Windows_Node"
                      }
                      steps {
                          echo "Task on Agent"
                      }
                   }
                   stage('Test On Master') {
                       agent {
                            label "master"
                       }
                       steps {
                           echo "Task on Master"
                       }
                   }
               }
           }
       }
    }   
