FROM stackbrew/ubuntu:saucy

RUN apt-get -y update
RUN apt-get -y install git-core python3
RUN apt-get -y install libsqlite3-dev
RUN apt-get -y install python3-pip
RUN apt-get -y install python3-apsw

RUN pip3 install bottle appdirs==1.2.0 prettytable==0.7.2 python-dateutil==2.2 requests==2.1.0 cherrypy==3.2.4 json-rpc==1.1 pycoin==0.25 pytest==2.5.1

RUN echo "#!/bin/bash\n\ncd /BoottleXCP && python3 counterpartyws.py" > /counterpartyws
RUN chmod 755 /counterpartyws

RUN git clone --recursive https://github.com/JahPowerBit/BoottleXCP.git /BoottleXCP

CMD "/counterpartyws"

