FROM centos:7
MAINTAINER GE Digital

 

RUN rm -f /var/lib/rpm/__*
RUN rpm --rebuilddb -v -v
RUN yum clean all

 


# Configure Yum Repos
RUN ls -l /etc/yum.repos.d/
RUN >Centos*.repo
COPY /repo/pwr_pulp_repos.repo /etc/yum.repos.d/pwr_pulp_repos.repo

 


RUN yum update all

 

RUN yum -v install -y \
    wget \
    zip \
    tar \
    unzip \
    && yum clean all

 


# see https://bugs.debian.org/775775
# and https://github.com/docker-library/java/issues/19#issuecomment-70546872
ENV CA_CERTIFICATES_JAVA_VERSION 20140324
