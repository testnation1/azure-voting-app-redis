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
                
                sh(script: """
                    docker build -t jenkins-pipeline .
                    docker images -a
                    cd azure-vote/
                    docker images -a
                    cd ..
                """)
               
            }     
                
        }
    }
}