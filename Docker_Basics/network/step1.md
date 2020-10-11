


`docker network create todo-app`{{execute}}

```
docker run -d \
    --network todo-app --network-alias mysql \
    --volume todo-mysql-data:/var/lib/mysql \
    --env MYSQL_ROOT_PASSWORD=secret \
    --env MYSQL_DATABASE=todos \
    --name my-mysql
    mysql:5.7
```{{execute}}


`docker exec -it my-mysql mysql -p`{{execute}}

`secret`{{copy}}

`SHOW DATABASES;`{{execute}}

```
docker run -dp 3000:3000 \
  --network todo-app \
  --env MYSQL_HOST=mysql \
  --env MYSQL_USER=root \
  --env MYSQL_PASSWORD=secret \
  --env MYSQL_DB=todos \
  --name my-todo-manager
  rogallo/101-todo-app:1.0.0
```{{ececute}}

`docker logs my-todo-manager`{{execute}}




`docker exec -it my-mysql mysql -p todos`{{execute}}


`select * from todo_items;`{{execute}}
