pipeline {
    agent any 

    parameters {
        string(name: 'MESSAGE', description: 'message', defaultValue: 'Testing Pipeline job')
        booleanParam(name: 'FAIL_BUILD', defaultValue: true, description: 'Testing failing build?')
    }

    stages {
        

        stage("Fail build stage") {
            when { expression { return params.FAIL_BUILD } }
            steps{
                bat 'echo "Failing" && exit 1'
            }
        }
        
        stage("Echo message") {
steps{
                bat "echo $MESSAGE"
            }
        }

        


    }

    post {
        always {
            bat "echo 'This is a post always action'"
        }

        success {
             bat "echo 'This is a post success action'"
        }

        failure {
             bat "echo 'This is a post failed action'"
        }
    }
}
