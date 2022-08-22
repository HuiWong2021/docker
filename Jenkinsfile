pipeline{
  agent any
   
  stages{
    stage("build"){
      
      stage('Build') {
            agent {
                docker {
                    image 'gradle:6.7-jdk11'
                    // Run the container on the node specified at the
                    // top-level of the Pipeline, in the same workspace,
                    // rather than on a new node entirely:
                    reuseNode true
                }
            }
            steps {
                sh 'gradle --version'
            }
        }
    
    stage("test"){
    
      steps{
        echo 'Testing the applicaton...'
        echo 'Run some Unit Test here to test the code'
        sh 'ls -l'
      }
    }
    
    stage("deploy"){
    
      steps{
        echo 'Deploying the application...'
        sh 'python3 helloworld.py'
      }
    }
  
  }
}
