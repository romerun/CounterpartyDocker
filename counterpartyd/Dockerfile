FROM stackbrew/ubuntu:saucy

RUN apt-get -y update
RUN apt-get -y install git-core python3
RUN git clone https://github.com/xnova/counterpartyd_build /counterpartyd_build
RUN cd /counterpartyd_build && sudo python3 setup.py; true
RUN mkdir -p /.config/counterpartyd && chown nobody.nogroup /.config/counterpartyd

ENTRYPOINT ["counterpartyd"]

USER nobody
