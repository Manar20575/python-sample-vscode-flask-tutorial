pipeline{
    agent{
        label "java"
    }
    environment{
        DOCKER_USER = credentials('dockerhub-user')
        DOCKER_PASS = credentials('dockerhub-password')
        def dockerT1 = new org.iti.docker()
    }
        parameters {
        string defaultValue: '${BUILD_NUMBER}', description: 'Current Image Version', name: 'VERSION'
    }
    stages{
        stage("build Docker image"){
            steps{
                dockerT1.build('python', "${VERSION}")
            }
        }
        stage("Push Docker image"){
            steps{
                    dockerT1.login("${DOCKER_USER}", "${DOCKER_PASS}")
                    dockerT1.push("${DOCKER_USER}", "${DOCKER_PASS}")
            }
        }
    }
}

// node('java'){
//     checkout scm
//     stage('build Docker image'){
//         sh "pwd && ls"
//         sh "docker build -t manar564/data-it:v${BUILD_NUMBER} ."
//     }
//     stage("Push Docker image"){
//         sh "docker push manar564/data-it:v${BUILD_NUMBER}"
//         }

// }
