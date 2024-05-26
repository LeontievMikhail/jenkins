### run 
docker build -t jenkins:jcasc .


### updating plugins using the console
docker exec  -it ubuntu-jenkins-1  /bin/bash


jenkins-plugin-cli --plugins update-sites-manager:2.0.0 --jenkins-plugin-info "https://mirror.yandex.ru/mirrors/jenkins/updates/update-center.json"


### list installed pluggins
java -jar jenkins-cli.jar -s http://ip172-18-0-145-cp6uj1aim2rg00apk5h0-8080.direct.labs.play-with-docker.com/ -auth jenkins:jenkinspassword list-plugins


java -jar jenkins-cli.jar -s http://192.168.0.134:8080/ -auth jenkins:jenkinspassword list-plugins
### list installed pluggins to file

java -jar jenkins-cli.jar -s  http://192.168.0.134:8080/  -auth jenkins:jenkinspassword groovy = < plugins.groovy > plugins.txt

jenkins-plugin-cli -f /usr/share/jenkins/ref/plugins.txt

jenkins-plugin-cli --plugins "snyk-security-scanner:2.12.1 file-operations:1.11 branch-api:2.5.6 pipeline-build-step:2.13 workflow-support:3.8 aws-credentials:1.28 subversion:2.13.1 github-branch-source:2.7.1 publish-over-ftp:1.15 cloudbees-folder:6.740.ve4f4ffa_dea_54"


java -jar jenkins-cli.jar -s http://192.168.0.134:8080/ -auth jenkins:jenkinspassword install-plugin branch-api:2.5.6


### move docker container
docker stop <container_name>
docker commit <container_name> <image_name>
docker save <image_name> -o file_name.tar
tar -cvf ./jenkins_data_vol.tar /var/lib/docker/volumes/jenkins_home/


scp file_name.tar user@server_ip:path

docker load < file_name.tar
sudo tar -xf jenkins_data_vol.tar -C /
#### docker cupmpose up -d  OR docker run -d --name <container_name> <image_name>




