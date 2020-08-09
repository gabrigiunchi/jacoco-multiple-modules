pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                script {
                    if (env.BRANCH_NAME == null) {
                        echo "branch is null"
                     } else {
                        echo env.BRANCH_NAME
                     }
                }
                bat 'mvn clean install'
            }
        }

        stage('SonarQube analysis') {
            steps {
                bat 'mvn sonar:sonar'
            }

        }
    }
}