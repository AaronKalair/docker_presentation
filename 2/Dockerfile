# Docker provides an ubuntu baselayer we can build ontop of
FROM ubuntu:14.04

# We want this to be one layer thats cached so make a really long bash command
RUN apt-get update && \
apt-get -y install \
 python-dev \
 python-setuptools \
 python-pip \
 curl

# Copy in our requirements file and install them seperately so we only
# do the time consuming install when the requirements change
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

# This is just a hint to whoever builds this image that this port
# needs to be forwarded, it doesn't actually do anything
# Note that if your running this example on a Mac you ALSO need to forward
# the port from Virtualbox to your host OS
EXPOSE 5000

# Sets envrionment variables
ENV FLASK_DEBUG 1
ENV FLASK_APP test_app/hello.py
# This will be the python process running as PID 1 inside the container
CMD ["flask",  "run"]
