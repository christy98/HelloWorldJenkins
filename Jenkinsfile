pipeline{
    agent any
    environment{
        NEW_VARIABLE = '1.1.1'
    }
    stages{
    
        stage("Build"){
          steps{
            echo "building the application..."
            echo "building the version ${NEW_VARIABLE}"  
          }    
        }
        stage("Test"){
            when{
                expression{
                    branch 'main'
                }
            }
            steps{
               echo "testing the application..."
            }   
        }
        stage("Deploy"){
          steps{
            echo "deploying the application..."
          }   
        }
    }
    post{
        success{
            echo "Pipeline is successful"
        }
    }
}
