README
======

Builds a simple Flask server running inside a container with the code
mounted in from the host OS allowing you to quickly make changes and test them

Build the image with `./build.sh`

Run it in a container with `./run.sh`

The webserver will be running on port 5000 inside the container, the
easiest way to interact with it is to exec a bash shell inside the running
container and use curl.

Alternatively you can forward the port to your host OS and use a web browser
but note that if you're doing this on a Mac you'll need to also forward the
port through virtualbox.
