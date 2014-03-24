FROM stackbrew/ubuntu:saucy

RUN apt-get -y update
RUN apt-get -y install git-core python3
RUN rev=99241e3c54ec3af74c1e0b8117da13998bbd24c2 git clone -b develop https://github.com/xnova/counterpartyd_build /counterpartyd_build
RUN cd /counterpartyd_build && sudo python3 setup.py; true
RUN mkdir -p /.config/counterpartyd && chown nobody.nogroup /.config/counterpartyd

ENV LANGUAGE en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8

RUN locale-gen en_US.UTF-8
RUN dpkg-reconfigure locales

ENTRYPOINT ["counterpartyd"]

USER nobody

