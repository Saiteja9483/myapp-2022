pipeline{
    parameters {
  choice choices: ['master', 'develop', 'qa'], description: 'branches parameterizing ', name: 'BranchName'
}
    agent any
    stages{
        stage("Maven Build"){
            when {
                branch "develop"
            }
            steps{
               sh "mvn package"
            }
        }
        
        stage("Deploy To Dev"){
            when {
                branch "develop"
            }
            steps{
               echo "deploying to development server...."
            }
        }
        stage("Deploy To production"){
            when {
                branch "master"
            }
            steps{
               echo "deploying to master server...."
            }
        }
    }
}
// testing github webhook
