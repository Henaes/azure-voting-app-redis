pipeline 
{
    agent any

    stages 
    {
        stage('Verify branch') 
        {
            steps 
            {
                echo "$GIT_BRANCH"
            }
        }
        
        stage('Docker build')
        {
            sh 'docker images -a'
            sh '''cd azure-vote/ 
                docker images-a 
                docker build -t jenkins-pipeline . 
                docker images -a 
                cd ..'''
        }
    }
}
