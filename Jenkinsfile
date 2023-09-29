pipeline{
    agent any
    stages{
        stage("Build the application"){
            steps{
            sh '''
            python lbg.py
            '''
            }
        }
        stage("Build docker image and publish "){
            steps{
            sh '''
            docker build -t gcr.io-docker.pkg.dev/lbg-mea-14/nm-pyt-app:latest .
            docker build -t gcr.io-docker.pkg.dev/lbg-mea-14/nm-pyt-app:{BUILD_NUMBER} .
            
            docker push gcr.io-docker.pkg.dev/lbg-mea-14/nm-pyt-app:latest
            docker push gcr.io-docker.pkg.dev/lbg-mea-14/nm-pyt-app:{BUILD_NUMBER} .

            docker run -d -p 80:8080 --name nm-pyt-app gcr.io-docker.pkg.dev/lbg-mea-14/nm-pyt-app:{BUILD_NUMBER}
            '''
            }
        }
        stage("Run unit tests"){
            steps{
            sh '''
            echo 'Running 0 tests'
            '''
            }
        }
    }    
}