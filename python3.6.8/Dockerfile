FROM centos:7.9.2009

#安装python3.6.8
COPY Python-3.6.8.tgz /tmp/Python-3.6.8.tgz
RUN yum install -y gcc openssl-devel bzip2-devel libffi-devel make
RUN tar -zxvf /tmp/Python-3.6.8.tgz -C /tmp  \
    && cd /tmp/Python-3.6.8  \
    && ./configure --prefix=/usr/local/python3  \
    && make  \
    && make install  \
    && rm -rf /tmp/Python-3.6.8 /tmp/Python-3.6.8.tgz  \
    && rm -rf /usr/bin/python3 /usr/bin/python  \
    && ln -s /usr/local/python3/bin/python3 /usr/bin/python  \
    && ln -s /usr/local/python3/bin/python3 /usr/bin/python3

ENV PATH=$PATH:/usr/local/python3/bin
ENV LANG=en_US.UTF-8
ENV LC_ALL=en_US.UTF-8
ENV PYTHONPATH=/usr/local/python3/lib/python3.6/site-packages