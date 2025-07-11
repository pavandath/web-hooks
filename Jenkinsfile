pipeline{
    agent any
    tools{
        jdk 'jdk-17'
    }
    stages{
      

        stage('CodeQuality'){
            steps{
                echo "**********RUNNING CODEQUALITY TEST***********"
                dir ('spring-petclinic'){
                sh '''
                mvn clean verify sonar:sonar \
  -Dsonar.projectKey=new \
  -Dsonar.host.url=http://34.135.134.147:9000 \
  -Dsonar.login=sqp_3e4d6ac7c47c17b9197a40b0eb526c7ca4061bbf
  -DskipTests 
                '''
                }
            }
        }
   
        }
   
    }
     
