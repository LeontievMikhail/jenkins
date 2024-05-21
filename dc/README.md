### run 
docker build -t jenkins:jcasc .


### updating plugins using the console
docker exec  -it ubuntu-jenkins-1  /bin/bash


jenkins-plugin-cli --plugins update-sites-manager:2.0.0 --jenkins-plugin-info "https://mirror.yandex.ru/mirrors/jenkins/updates/update-center.json"
