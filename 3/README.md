README
======

A simple app that runs two Flask apps inside containers, where app1 can
communicate with app2 via Docker links

To build and run - `docker-compose up -d`

If you exec a bash shell into app1 you'll be able to communicate with app2
using the app2 DNS name
