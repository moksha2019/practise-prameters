pipeline {
    agent {
        label 'java-node'
    }
    parameters {
        string(name: CHG_TKT, defaultValue: CHG12345, description: 'Enter the  change  ticket number:')
        booleanParam(name: 'SRE_APPROVE', defaultValue: true, description: 'Is change SRE approved')
        choice(name: 'CHOICES', choices: ['DEV', 'STAGE', 'PROD'], description: 'Please Select the  Environment')
    }
    stages {
        stage ('Build stage') {
            steps {
                echo "Build completed: "
            }
        }
        stage ('Sonar stage'){
            steps {
                echo "scanning completed: "
            }
        }
        stage ('Dev devoply') {
            steps {
                echo "Deploy to dev  completed"
            }
        }
        stage ('stage devoply') {
            steps {
                echo "Deploy to stage  completed"
            }
        }
        stage ('Production devoply') {
            when {
                expression { params.CHOICES == 'PROD'} 
            }
            steps {
                echo "Deploy to Production completed: "
            }
        }
    }
}
