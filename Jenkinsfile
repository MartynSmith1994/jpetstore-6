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
                withCredentials([sshUserPrivateKey('b7e92b46-352a-460c-b8c4-c140f48af75f']) 
                {
                    sh 'scp /Users/Shared/Jenkins/Home/workspace/useCaseTest/target/jpetstore.war ubuntu@52.212.53.70:/opt/apache-tomcat-9/webapps/'
                }
                
                echo 'Deployed.'
            }
        }
    }
}
