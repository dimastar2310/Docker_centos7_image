# Docker_centos7_image <br>
<br>proper installation centos
<br>docker build -t custom-centos:7 .  => we have proper repos
<br>docker run --privileged -d custom-centos:7 => we want systemctl to work ,and running in detached mode
<br>docker exec -it <container_id>  /bin/bash  => running the container

