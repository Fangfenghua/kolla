FROM %%KOLLA_NAMESPACE%%/%%KOLLA_PREFIX%%nova-base:%%KOLLA_TAG%%
MAINTAINER Kolla Project (https://launchpad.net/kolla)

RUN export http_proxy=http://3.6.1.35:808 \
         && export https_proxy=http://3.6.1.35:808 \
         && yum -y install openstack-nova-compute openvswitch\
         sysfsutils && yum clean all

ADD config-nova-compute.sh /opt/kolla/config-nova-compute.sh

ADD ./start.sh /start.sh

VOLUME [ "/sys/fs/cgroup" ]

CMD ["/start.sh"]
