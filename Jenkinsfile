node {

stage('Clone Repository')
{
checkout scm
}


stage('Show me the files')
{
sh "ls -l"
}


stage('Build Docker Image and push image to DockerHub')

{
sh "docker build -t martingikonyotest:version1 ."
}
  
stage('Docker login to hub and push the image'){
sh "docker login -u 'gikonyogiks' -p 'L@ndrover2018'"
sh "docker tag martingikonyotest:version1 gikonyogiks/martingikonyotest:version1"
sh "docker push gikonyogiks/martingikonyotest:version1"
}


stage('Run Container')
{
sh "docker container run  --detach --publish 6683:6683 --name devopstest gikonyogiks/martingikonyotest:version1"
}
}
