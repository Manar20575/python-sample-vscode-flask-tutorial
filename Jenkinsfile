node('java'){
    stage('build Docker image'){
        sh "pwd && ls"
        sh "docker build -t manar564/data-it:v${BUILD_NUMBER} ."
    }
    stage("Push Docker image"){
        sh "docker push manar564/data-it:v${BUILD_NUMBER}"
        }

}
