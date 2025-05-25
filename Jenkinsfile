node('Java'){
    stage('build Docker image'){
        sh "docker build -t manar564/data-it:v${BUILD_NUMBER} ."
    }
    stage("Push Docker image"){
            steps{
                sh "docker push manar564/data-it:v${BUILD_NUMBER}"
            }
        }

}