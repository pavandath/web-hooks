pipeline{
    agent any
    
    stages{
      

        stage('CodeQuality'){
            
            steps{
                echo "**********RUNNING CODEQUALITY TEST***********"
                sh "git clone https://github.com/chandupolina/spring-petclinic.git"
                dir ('spring-petclinic'){
                sh "mvn clean verify sonar:sonar \
                    -Dsonar.projectKey=petclinic \
                    -Dsonar.host.url='http://34.133.89.244:9000' \
                    -Dsonar.login=sqp_102653f8646b59eedf7f0b7c0cd5185ebab12ee8"
                }
            }
        }
   
        }
   
    }
     
