1. Загрузите образ node версии 15.14
```shell
docker pull node:15.14-alpine
```

2. Запустите контейнер node в интерактивном режиме подключения терминала, поименуйте его mynode, передайте две переменные среды NAME=<ваше имя> и SURNAME=<ваша фамилия>

```shell
docker run --name mynode -e NAME=DMITRY -e SURNAME=UKOLOV -it node:15.14-alpine 
```

3. В интерактивной среде выполнения node выполните скрипт, который выведет на экран приветсвтие: Привет, <ваше имя> <ваша фамилия>!, эти данные должны быть получены из переменных среды

```shell
console.log(`Привет, ${process.env.NAME} ${process.env.SURNAME}!`)

> Привет, DMITRY UKOLOV!
```

4. Остановите контейнер
```shell
docker stop mynode
```

5. Удалите образ node версии 15.14
```shell
docker rmi node:15.14-alpine
```
