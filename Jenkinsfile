pipeline 
{
    agent any

    stages {
        stage('Verify branch') 
        {
            steps 
            {
                echo $GIT_BRANCH
            }
        }
        stage('Fix 5 branch') 
        {
            steps 
            {
                echo 'Something changed'
            }
        }

        stage('Docker Build')
        {
            steps
            {
                pwsh(script: 'docker images -a'
                pwsh(script: '''cd azure-vote/ 
                docker images-a 
                docker build -t jenkins-pipeline . 
                docker images -a 
                cd ..
                ''')
            }
        }
    }
}
