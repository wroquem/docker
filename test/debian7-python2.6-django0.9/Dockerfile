FROM wroque/debian7-python2.6:1

MAINTAINER Miguel Neyra

WORKDIR /opt

RUN curl -L -o django-stable-0.96.tar.gz "https://drive.google.com/uc?export=download&id=1LoW1n2dI5W4aiQrOx979D59iDRrzQLrU"
RUN tar -xzvf django-stable-0.96.tar.gz && cd django-stable-0.96.x && python setup.py install && cd ..

