pipeline{
    agent{
        node{
            label 'master'
            customWorkspace '/mnt/docker/2022Q3'
        }
    }
    stages{
        stage ('create container'){
            steps{
                /*sh "docker kill container3"
                sh "docker rm container3"*/
                sh "docker run --name container3 -itdp 200:80 httpd"
            }
        }
        stage ('deploy indexfile'){
            steps{
                sh "chmod 777 -R index.html"
                sh "docker cp index.html container3:/usr/local/apache2/htdocs"
            }
        }
    }
}
