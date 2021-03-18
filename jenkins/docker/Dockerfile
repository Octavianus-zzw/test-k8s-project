FROM jenkins/jenkins:lts
USER root
RUN apt-get update && apt-get install -y apt-transport-https curl
WORKDIR /tmp
RUN curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
RUN echo "deb https://mirrors.aliyun.com/kubernetes/apt/ kubernetes-xenial main" >> /etc/apt/sources.list.d/kubernetes.list 
RUN apt-get update && apt-get install -y kubectl
WORKDIR /var/jenkins_home
USER jenkins
ENTRYPOINT ["/bin/tini", "--", "/usr/local/bin/jenkins.sh"]