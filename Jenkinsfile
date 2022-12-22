pipeline{
    agent{
        node{
            label 'master'
            customWorkspace '/mnt/docker/2022Q1'
        }
    }
    stages{
        stage ('create container'){
            steps{
                /*sh "docker kill container1"
                sh "docker rm container1"*/
                sh "docker run --name container1 -itdp 70:80 httpd"
            }
        }
        stage ('deploy indexfile'){
            steps{
                sh "chmod 777 -R index.html"
                sh "docker cp index.html container1:/usr/local/apache2/htdocs"
            }
        }
    }
}
