pipeline {

    agent any

    stages {

        stage("Lint"){

            steps{

                echo "Running the linter"

            }

        }

        stage("Run Tests") {

            parallel{

                stage("Testing on Windows") {

                    steps {

                        echo "Testing on Windows"

                    }

                }

                stage("Testing on Linux") {

                    steps {

                        echo "Testing on Linux"

                    }

                }

            }

        }

    stage("Deploy") {

        steps {

            echo "Deploying your app"

            sh """echo "\$(date) - INFO: Dummy log line" > logs.txt """
            sh """sleep 30 """

        }

    }

    }

    post {

       always {

          archiveArtifacts "logs.txt"

       }

    }

}


