1. Загрузите образ node версии 15.14

```shell
docker pull node:latest
```

2. Запустите контейнер с именем first_node из образа node версии 15.14 в фоновом режиме, подключив папку data из текущей директории в /var/first/data контейнера
```shell
docker run --name first-node -it -v $PWD/data:/var/first/data node
```

3. Запустите контейнер с именем second_node из образа node версии 15.14 в фоновом режиме, подключив папку data из текущей директории в /var/second/data контейнера
```shell

docker run --name second-node -it -v $PWD/data:/var/second/data node
```

4. Подключитесь к контейнеру first_node с помощью exec и создайте текстовый файл любого содержания в /var/first/data
```shell
docker exec -it first-node /bin/bash

cd var/first/data

touch from-first-node.txt
```

6. Подключитесь к контейнеру second_node с помощью exec и получите список файлов в директории /var/second/data, выведете на экран содержимое файлов
```shell
docker exec -it first-node /bin/bash

cd var/second/data

ls

> from-first-node.txt  from-host.txt
```

7. Остановите оба контейнера

```shell
docker stop first-node
docker stop second-node
```

8. Удалите оба контейнера
```shell
docker rm first-node
docker rm second-node
```

9. Удалите образ node версии 15.14
```shell
docker rmi node:latest
```

