FROM amazonlinux:1

RUN yum install -y clamav -x clamav-data
COPY etc /etc/

RUN curl https://secure.eicar.org/eicarcom2.zip > eicar2.zip

CMD ["clamdscan", "--config-file=/etc/clamdscan.conf", "eicar2.zip"]
