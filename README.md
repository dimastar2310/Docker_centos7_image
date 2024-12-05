# Docker_centos7_image
*proper installation centos
*docker build -t custom-centos:7 .  => we have proper repos
*docker run --privileged -d custom-centos:7 => we want systemctl to work ,and running in detached mode
*docker exec -it <container_id>  /bin/bash  => running the container

