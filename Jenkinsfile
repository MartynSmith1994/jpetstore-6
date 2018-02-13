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
                sh 'sudo cp /Users/Shared/Jenkins/Home/workspace/useCaseTest/target/jpetstore.war /Users/martyn/apache-tomcat-9.0.5/webapps/'
                echo 'Deployed.'
            }
        }
    }
}
