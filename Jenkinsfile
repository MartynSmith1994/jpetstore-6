pipeline 
{
    agent any
    tools
    {
        maven "maven-3.5.2"
        jdk "1.8.0_161” 
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
