FROM debian:7

MAINTAINER Miguel Neyra

# runtime dependencies
RUN apt-get update && apt-get -y install python2.6 && apt-get -y install python2.6-dev && ln -s /usr/bin/python2.6 /usr/bin/python
RUN apt-get -y install libmysqlclient-dev
# install tools
RUN apt-get -y install curl
RUN apt-get -y install procps

WORKDIR /opt

RUN curl -L -o setuptools-15.2.tar.gz "https://drive.google.com/uc?export=download&id=1YbOOadkVkxuD9tULfObvJawmFgffswrJ"
RUN curl -L -o pip-6.1.1.tar.gz "https://drive.google.com/uc?export=download&id=1wTHRiXEsvb4cTS6UYBOby3QM6lV3NqFP"

RUN tar -xzvf setuptools-15.2.tar.gz && cd setuptools-15.2 && python setup.py install && cd ..
RUN tar -xzvf pip-6.1.1.tar.gz && cd pip-6.1.1 && python setup.py install && cd ..
