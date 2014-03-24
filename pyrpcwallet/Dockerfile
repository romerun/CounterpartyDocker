FROM stackbrew/ubuntu:saucy

RUN apt-get -y update
RUN apt-get -y install git-core python3
RUN apt-get -y install libsqlite3-dev
RUN apt-get -y install python3-pip
RUN apt-get -y install python3-apsw

RUN pip3 install bottle appdirs==1.2.0 prettytable==0.7.2 python-dateutil==2.2 requests==2.1.0 cherrypy==3.2.4 json-rpc==1.1 pycoin==0.25 pytest==2.5.1
RUN pip3 install bottle pycoin pycrypto

RUN rev=bdeef54ca74ebd5990350d62b57280d970af3c04 git clone https://github.com/JahPowerBit/pyrpcwallet.git /pyrpcwallet

RUN echo "#!/bin/bash\ncd /pyrpcwallet && python3 pyrpcwallet.py --rpc-host=0.0.0.0 --rpc-port=8383 \$1 \$2 \$3 \$4 \$5 \$6 \$7 \$8 \$9" > /wallet
RUN chmod 755 /wallet

ENTRYPOINT ["/wallet"]
