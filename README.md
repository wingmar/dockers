# dockers

## kong
1. start postgres
`sudo docker run --name psql -e POSTGRES_PASSWORD=mysecretpassword -it --net host postgres`
2. build kong docker
`sudo docker build . -t kong`
3. run kong docker
`sudo docker run --name kong -p 8000:8000 -p 8001:8001 -p 8443:8443 -p 46:7946 --net host -it kong`
