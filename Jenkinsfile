pipeline{
    agent any
    stages{
        stage ('BUILD'){
            steps{
                echo "********************Building the code**********************"
                sh 'rm -rf spring-petclinic'   
                sh 'git clone https://github.com/pavandath/spring-petclinic.git'
                dir ('spring-petclinic'){
                sh 'mvn clean package -DskipTests -Dcyclonedx.skip=true'
                stash name: 'build-jar', includes: 'target/*.jar'   
            }
            }
        }

        stage('CodeQuality'){
            steps{
                echo "**********RUNNING CODEQUALITY TEST***********"
                dir ('spring-petclinic'){
                sh """
                mvn clean verify sonar:sonar \  
                    -Dsonar.projectKey=new \
                    -Dsonar.host.url=http://34.135.134.147:9000 \
                    -Dsonar.login=sqp_75dffea6f61762e7f95f5ef40d60f6c9fd4a0ab5

                """
                }
            }
        }
   
        }
   
    }
     
