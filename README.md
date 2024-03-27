## without root         | require updating `SUPER, REPLICATION CLIENT`
docker run -d \
  --name mysql-container \
  -p 3306:3306 \
  -v ./mysql.cnf:/etc/mysql/my.cnf \
  -e MYSQL_ROOT_PASSWORD=123 \
  -e MYSQL_DATABASE=maxwell \
  -e MYSQL_USER=max \
  -e MYSQL_PASSWORD=1234 \
  mysql:latest


## root
docker run -d \
  --name mysql-container \
  -p 3306:3306 \
  -v ./mysql.cnf:/etc/my.cnf \
  -e MYSQL_ROOT_PASSWORD=123 \
  -e MYSQL_DATABASE=maxwell \
  mysql:latest


## get your local IP
```
ip addr show |grep 192
```
> above is ubuntu debian-based,

### make sure to adjust IP in values.yaml, allowing maxwell to communicate to localhost mysql