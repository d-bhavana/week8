pipeline{
    agent any
        stages{
            stage('Build'){
                steps{
                    echo "Build Docker Image"
                    bat "docker build -t mypythonflaskapp ."
                }
            }
            stage('Run'){
                steps{
                    echo "Run applictaion in Docker Container"
                    bat "docker rm -f mycontainer || exit0"
                    bat "docker run -d -p 5000:5000 --name mycontainer mypythonflaskapp"
                } 
            }

        
        }
        post{
            success{
                echo "pipeline completed sucessfully"
            }
            failure{
                echo "pipeline failed.Please check the logs"
            }
        }
}
