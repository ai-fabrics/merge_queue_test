pipeline {
    agent { label 'rocky' }
    options {
        disableConcurrentBuilds(abortPrevious: true)
        //throttleJobProperty(
        //    categories: ['A1SiliconBuilds'],
        //    throttleEnabled: true,
        //    throttleOption: 'category',
        //)
    }
    //environment {
    //  // Define Jenkins environment variables
    //}

    stages {
        stage('Dummy build') {
            steps {
                script {
                    sh """
                    RUN_TIME=`expr \$RANDOM % 60`
                    echo "Run (sleep) time for dummy build: "
                    sleep \$RUN_TIME
                    """
                }
            }
        }
        stage('stage 1') {
            steps {
                script {
                    sh """
                    echo "Run (sleep) time for stage 1"
                    sleep 200 
                    """
                }
            }
        }
    }
    post {
        always {
            // Clean up workspace
            echo "Cleaning up workspace"
            deleteDir()
        }
    }
}

