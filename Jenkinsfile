pipeline {
    agent any

      stages {

    stage("Istall dependacies"){

      steps{
        echo 'install dependacies'
      }

    }

    stage("Build"){

      steps{
        echo 'testing application'
      }

    }

    stage("Deploy to Render"){

      steps{
        echo 'deploying application'
      }

    }
    post {
        success {
            emailext attachLog: true,
                body:
                    """
                    <p>EXECUTED: Job <b>\'${env.JOB_NAME}:${env.BUILD_NUMBER})\'</b></p>
                    <p>
                    View console output at
                    "<a href="${env.BUILD_URL}">${env.JOB_NAME}:${env.BUILD_NUMBER}</a>"
                    </p>
                      <p><i>(Build log is attached.)</i></p>
                    """,
                subject: "Status: 'SUCCESS' -Job \'${env.JOB_NAME}:${env.BUILD_NUMBER}\'",
                to: 'mukheboe@gmail.com'
        }
        failure {
            emailext attachLog: true,
                body:
                    """
                    <p>EXECUTED: Job <b>\'${env.JOB_NAME}:${env.BUILD_NUMBER})\'</b></p>
                    <p>
                    View console output at
                    "<a href="${env.BUILD_URL}">${env.JOB_NAME}:${env.BUILD_NUMBER}</a>"
                    </p>
                      <p><i>(Build log is attached.)</i></p>
                    """,
                subject: "Status: FAILURE -Job \'${env.JOB_NAME}:${env.BUILD_NUMBER}\'",
                to: 'mukheboe@gmail.com'
        }
}
}
}
