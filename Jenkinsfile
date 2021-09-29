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
        
       stage('Build') 
       {
            agent 
            {

                label 'jenkins-slave-swat-prod-01'
            }

            steps 
            {
                script 
                {
                    docker.image('mysql:latest').withRun('-e "MYSQL_ROOT_PASSWORD=password" -e "MYSQL_DATABASE=scheduler" -p 3306:3306') { c ->
                        docker.image('maven').inside("--privileged -v $HOME/.m2:/home/jenkins/.m2 -ti -u 496 -e MAVEN_CONFIG=/home/jenkins/.m2 -e MAVEN_OPTS=-Xmx2048m --link ${c.id}:localhost") {
                    maven.cleanPackage()
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

