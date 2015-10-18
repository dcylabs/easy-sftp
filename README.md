# Usages 
## Deployment 
### Docker 
```
docker run -d -v /path/to/sftp-config.json:/config/sftp-config.json:ro -v ./data/user1:/sftp/user1/data -v ./data/user2:/sftp/user2/data -p "22:22" dcylabs/easy-sftp
```
### docker-compose.yml 
```
sftp:
  image: dcylabs/easy-sftp
  volumes:
    - ./data/user1:/sftp/user1/data
    - ./data/user2:/sftp/user2/data
    - /path/to/sftp-config.json:/config/sftp-config.json:ro
  ports:
    - "22:22"
```
## Configuration 
You can easily configure your jailed users with the *sftp-config.json*
```
[
  {"name": "user1", "password": "user1pass"},
  {"name": "user2", "password": "user2pass"}
]
```
