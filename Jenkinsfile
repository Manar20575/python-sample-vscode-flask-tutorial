node{
    agent{
        label "java"
    }
    stage('build Docker image'){
        sh "docker build -t manar564/pipline-2:v${BUILD_NUMBER} ."
    }
    stage("Push Docker image"){
            steps{
                sh "docker push manar564/pipline-2:v${BUILD_NUMBER}"
            }
        }

}
