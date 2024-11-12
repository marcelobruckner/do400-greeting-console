pipeline{
    agent{
        label "nodejs"
    }
    stages{
        stage('Check NODE_ENV') {
            steps {
                script {
                    echo "NODE_ENV: ${env.NODE_ENV}"
                }
            }
        }
        stage("Install dependencies"){
            steps{
                sh "npm ci"
            }
        }

        stage("Check Style"){
            steps{
                sh "npm run lint"
            }
        }

        stage("Test"){
            steps{
                sh "npm test"
            }
        }

        stage('Release'){
            steps{
                sh '''
                    oc project dfmhdb-greetings
                    oc start-build greeting-console --follow --wait    
                '''
            }
        }
    }
}
