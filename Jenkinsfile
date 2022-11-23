pipeline{
    agent any
    
    stages{
    
        stage("Build"){
          steps{
            echo "building the application..."
          }    
        }
        stage("Test"){
            when{
                expression{
                    BRANCH_NAME == "dev"
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
