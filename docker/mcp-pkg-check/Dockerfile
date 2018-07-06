FROM ubuntu:xenial
RUN echo 'apt-get -qq update && apt-cache policy $@' > /bin/listpkgs.sh
ADD repo.list /etc/apt/sources.list.d/repo.list
ADD http://apt.mirantis.com/public.gpg /tmp/apt.mirantis.com.gpg
RUN apt-key add /tmp/apt.mirantis.com.gpg
ADD http://mirror.mirantis.com/nightly/openstack-pike/xenial/archive-pike.key /tmp/mirror.mirantis.com.gpg
RUN apt-key add /tmp/mirror.mirantis.com.gpg
ENTRYPOINT ["/bin/sh", "/bin/listpkgs.sh"]
