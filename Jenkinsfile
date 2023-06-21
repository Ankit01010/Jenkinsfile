pipeline {
    agent any
   
    environment {
       myname='Sunny'
    }
    
    parameters {
        string (name:'person', defaultValue : 'Ankit Singh', description :"Who are you?")
        booleanParam(name:'isMale', defaultValue: true, description:"")
        choice(name:'City', choices:[ 'Patna', "Samastipur",'Darbhanga'], description:"")
    }
    stages {
        stage('Run A command') {
            steps {
                sh '''
                ls
                pwd
                date
                
                '''
              
            
                
            }
        }
        stage('Enviroment Variable') {
            environment {
                name = 'Ankit'
            }
            steps {
                sh 'echo "${BUILD_ID}"'
                sh 'echo "${name}" '
                sh 'echo "${myname}" '
                
            }
        }
        stage('Parameter') {
            steps {
                echo 'Deploy on test'
                sh 'echo "${person}" '
                sh 'echo "${isMale}" '
            }
        }
        stage('Continue ? ') {
            input{
                message "Should we continue?"
                ok "Yes we Should"
                
            }
            steps {
                echo 'Deploy on prod'
            }
        }
        stage('Deploy on prod') {
            steps {
                echo 'Deploy on prod'
            }
        }
    }
    post {
        always{
            echo 'i will always say hello again!'
        }
        failure{
            echo 'Failure'
        }
        success{
            echo 'Success'
        }
    }
}
