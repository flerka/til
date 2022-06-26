## Run mongodb on specific port 27020-27022 in our case
```
docker run -d -p 27020-27022:27017-27019 --name mongodb mongo
```

## Copy file from Windows host to linux container
```
docker cp file-name container-id:/home/
```

## Run mongodb bash in docker container
```
docker exec -it mongodb bash
```