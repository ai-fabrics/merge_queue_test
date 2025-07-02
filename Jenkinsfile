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
                    echo "Run (sleep) time: \$RUN_TIME"
                    sleep \$RUN_TIME
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

