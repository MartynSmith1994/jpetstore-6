pipeline 
{
    agent any
    tools
    {
        maven 'Maven 3.5.2'
        jdk 'jdk8'
    }
    stages 
    {
        stage('Build') 
        {
            steps 
            {
                echo 'Building..'
                sh 'mvn clean verify'
            }
            post
            {
                success
                {
                     stage('Test') 
                     {
                        steps 
                         {
                            echo 'Testing..'
                            junit 'target/surefire-reports/*.xml'
                         }
                     }
                 }
            }
       
        }
        stage('Deploy') 
        {
            steps 
            {
                echo 'Deploying....'
            }
        }
    }
}
