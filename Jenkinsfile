pipeline{
    agent{
        label "nodejs"
    }
    stages{
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
    }
}
