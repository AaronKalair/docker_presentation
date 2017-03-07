# Docker provides an ubuntu baselayer we can build ontop of
FROM ubuntu:14.04

# We want this to be one layer thats cached so make a really long bash command
RUN apt-get update && \
apt-get -y install \
 python-dev \
 python-setuptools \
 python-pip

# Copy in our requirements file and install them seperately so we only
# do the time consuming install when the requirements change
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

# Copy in the main code
COPY test_app/ test_app/

# This will be the python process running as PID 1 inside the container
CMD ["python", "-u",  "test_app/worker.py"]
