pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Docker Build') {
            steps {
               sh(script: 'docker images ls')
               sh(script: """
                 cd azure-vote/
                 docker images ls
                 docker build -t jenkins-pipeline .
                 docker images -a
                 cd ..
               """)
            }
        }   
    }
}