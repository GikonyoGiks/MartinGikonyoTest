node {

stage('Clone Repository')
{
checkout scm
}


stage('Show me the files')
{
sh "ls -l"
sh "pwd"
}


stage('Build Docker Image and push image to DockerHub')

{
sh "sudo docker build -t martingikonyotest:version1 ."
}
  
stage('Docker login to hub and push the image')
{
sh "sudo docker login -u 'gikonyogiks' -p 'L@ndrover2018'"
sh "sudo docker tag martingikonyotest:version1 gikonyogiks/martingikonyotest:version1"
sh "sudo docker push gikonyogiks/martingikonyotest:version1"
}


stage('Run Container')
{
sh "sudo docker container run  --detach --publish 6683:6683 --name devopstest gikonyogiks/martingikonyotest:version1"
}
}
