pipeline {
    agent any

    stages {
        stage ('Build Image') {
            steps {
                script {
                    dockerapp = docker.build("gabriel7cd/vuetscript:${env.BUILD_ID}", '-f ./Dockerfile ./') 
                }                
            }
        }

        stage ('Push Image') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {
                        dockerapp.push('latest')
                        dockerapp.push("${env.BUILD_ID}")
                    }
                }
            }
        }

        stage ('Deploy Kubernetes') {
            environment {
                tag_version = "${env.BUILD_ID}"
            }
            steps {
                withKubeConfig([credentialsId: 'kubeconfig']) {
                    sh 'sed -i "s/{{tag}}/$tag_version/g" ./deployment.yaml'
                    sh 'kubectl apply -f ./deployment.yaml'
                }
            }
        }
    }

    post {
        always {
            script {
                    sh "docker rmi -f gabriel7cd/vuetscript:${env.BUILD_ID}"
                    sh "docker rmi -f registry.hub.docker.com/gabriel7cd/vuetscript:${env.BUILD_ID}" 
                    sh "docker rmi -f registry.hub.docker.com/gabriel7cd/vuetscript:latest"
            }
        }
    }
}
