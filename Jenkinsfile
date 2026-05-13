pipeline {   
    agent any
    parameters {
        choice(name: 'ENV', choices: ['dev', 'qa', 'prod'], description: 'Select the environment to deploy')
        booleanParam(name: 'executeTest', defaultValue: true, description: 'Test Execution')
}
    stages {
        stage("build") {
            steps {
                script {
                    echo 'Build started...'
                }
            }
        }
        stage("test") {
         when {
                            expression { params.executeTest }
                        }
            steps {

                script {
                    echo 'Test Started...'
                }
            }
        }

        stage("Deploy") {
            steps {
                script {
                    echo 'Deployed...'
                }
            }
        }            
    }
} 
