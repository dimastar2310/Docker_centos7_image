FROM centos:7

# Set environment variable
ENV container docker

# Copy the modified CentOS-Base.repo file
COPY CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo

# Clean and update yum repositories
RUN yum clean all && yum -y update

# Remove unnecessary systemd files for Docker image optimization
RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == \
systemd-tmpfiles-setup.service ] || rm -f $i; done); \
    rm -f /lib/systemd/system/multi-user.target.wants/*; \
    rm -f /etc/systemd/system/*.wants/*; \
    rm -f /lib/systemd/system/local-fs.target.wants/*; \
    rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
    rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
    rm -f /lib/systemd/system/basic.target.wants/*; \
    rm -f /lib/systemd/system/anaconda.target.wants/*;

# Set volume for cgroup
VOLUME [ "/sys/fs/cgroup" ]

# Set default command to run init
CMD ["/usr/sbin/init"]



#EXPOSE 80 443 22 5432
