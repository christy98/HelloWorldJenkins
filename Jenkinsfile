pipeline{
    agent any
    environment{
        NEW_VARIABLE = '1.1.1'
    }
    tools{
        maven 'Maven'
    }
    parameters {
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
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
                    params.executeTests
                }
            }
            steps{
               echo "testing the application..."
            }   
        }
        stage("Deploy"){
          steps{
            echo "deploying the application..."
              echo "${VERSION}"
          }   
        }
    }
    post{
        success{
            echo "Pipeline is successful"
        }
    }
}
