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

        stage('Initialize')
        {
            steps
            {

                def dockerHome = tool 'myDocker'
                env.PATH = "${dockerHome}/bin:${env.PATH}"
            }
            
        }
        
        stage('Docker build')
        {
            steps
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
}
