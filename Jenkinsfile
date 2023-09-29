pipeline{
    agent any
    stages{
        stage("Build docker image and publish "){
            steps{
            sh '''
            docker build -t gcr.io/lbg-mea-14/nm-pyt-app:latest .
            docker build -t gcr.io/lbg-mea-14/nm-pyt-app:${BUILD_NUMBER} .
            
            docker push gcr.io/lbg-mea-14/nm-pyt-app
            docker push gcr.io/lbg-mea-14/nm-pyt-app:${BUILD_NUMBER} .

            '''
            }
        }
        stage("Cleanup Jenkins"){
            steps{
            sh '''
            docker rmi gcr.io/lbg-mea-14/nm-pyt-app
            docker push gcr.io/lbg-mea-14/nm-pyt-app:${BUILD_NUMBER}
            '''
            }
        }
        stage ("Deploy Containers"){
            steps{
                sh '''

                ssh jenkins@naresh-app-server << EOF
                
                docker pull gcr.io/lbg-mea-14/nm-pyt-app:${BUILD_NUMBER}

                docker run -d -p 80:8080 --name nm-pyt-app gcr.io/lbg-mea-14/nm-pyt-app:${BUILD_NUMBER}
                
                '''
            }
        }
    }    
}