# dockers

## kong
`sudo docker build . -t kong`
`sudo docker run --name kong -p 8000:8000 -p 8001:8001 -p 8443:8443 -p 46:7946 --net host -it kong`
