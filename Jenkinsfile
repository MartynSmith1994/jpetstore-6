pipeline 
{
    agent any
    tools
    {
        maven "maven-3.5.2"
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
       
        }
        stage('Test') 
           {
           steps 
                {
                    echo 'Testing..'
                    junit 'target/surefire-reports/*.xml'
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
