FROM centos:7.9.2009

#安装jer
COPY go1.18.linux-amd64.tar.gz /tmp/go1.18.linux-amd64.tar.gz
RUN tar -zxvf /tmp/go1.18.linux-amd64.tar.gz -C /usr/local \
    && rm -rf /tmp/go1.18.linux-amd64.tar.gz \
    && echo "export PATH=$PATH:/usr/local/go/bin" >> /etc/profile \
    && source /etc/profile \
    && go version \
    && go env \
    && go env -w GO111MODULE=on \
    && go env -w GOPROXY=https://goproxy.cn,direct \
    && yum update -y \
    && yum install -y wget tar git gcc+ gcc-c++ make automake autoconf libtool \
    && yum clean all