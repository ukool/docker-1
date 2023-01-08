1. Загрузите образ busybox последней версии
```shell
docker pull busybox
```

2. Запустите новый контейнер busybox с командой ping сайта netology.ru, и количеством пингов 7, поименуйте контейнер pinger
```shell
docker run --name pinger busybox ping netology.ru -c 7
```

3. Выведите на список всех контейнеров - запущенных и остановленных

```shell
 docker ps -a
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS                          PORTS     NAMES
346e620fddb4   busybox   "ping netology.ru -c…"   About a minute ago   Exited (0) About a minute ago             pinger
```

4. Выведите на экран логи контейнера с именем pinger

```shell
docker logs -t pinger

2023-01-07T17:30:34.301566052Z PING netology.ru (188.114.98.234): 56 data bytes
2023-01-07T17:30:34.301601760Z 64 bytes from 188.114.98.234: seq=0 ttl=37 time=54.988 ms
2023-01-07T17:30:35.304113719Z 64 bytes from 188.114.98.234: seq=1 ttl=37 time=55.836 ms
2023-01-07T17:30:36.303325053Z 64 bytes from 188.114.98.234: seq=2 ttl=37 time=54.282 ms
2023-01-07T17:30:37.310303303Z 64 bytes from 188.114.98.234: seq=3 ttl=37 time=57.577 ms
2023-01-07T17:30:38.313236846Z 64 bytes from 188.114.98.234: seq=4 ttl=37 time=55.323 ms
2023-01-07T17:30:39.318580429Z 64 bytes from 188.114.98.234: seq=5 ttl=37 time=55.478 ms
2023-01-07T17:30:40.318366388Z 64 bytes from 188.114.98.234: seq=6 ttl=37 time=54.675 ms
2023-01-07T17:30:40.318475513Z 
2023-01-07T17:30:40.318490263Z --- netology.ru ping statistics ---
2023-01-07T17:30:40.318497138Z 7 packets transmitted, 7 packets received, 0% packet loss
2023-01-07T17:30:40.318561513Z round-trip min/avg/max = 54.282/55.451/57.577 ms
```

5. Запустите второй раз контейнера с именем pinger

```shell
docker stop pinger
docker start pinger  
```

6. Выведите на список всех контейнеров - запущенных и остановленных
```shell
docker ps -a  
CONTAINER ID   IMAGE     COMMAND                  CREATED         STATUS                      PORTS     NAMES
346e620fddb4   busybox   "ping netology.ru -c…"   4 minutes ago   Exited (0) 59 seconds ago             pinger

docker ps   
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
```

7. Выведите на экран логи контейнера с именем pinger

```shell
docker logs -t pinger
2023-01-07T17:30:34.301566052Z PING netology.ru (188.114.98.234): 56 data bytes
2023-01-07T17:30:34.301601760Z 64 bytes from 188.114.98.234: seq=0 ttl=37 time=54.988 ms
2023-01-07T17:30:35.304113719Z 64 bytes from 188.114.98.234: seq=1 ttl=37 time=55.836 ms
2023-01-07T17:30:36.303325053Z 64 bytes from 188.114.98.234: seq=2 ttl=37 time=54.282 ms
2023-01-07T17:30:37.310303303Z 64 bytes from 188.114.98.234: seq=3 ttl=37 time=57.577 ms
2023-01-07T17:30:38.313236846Z 64 bytes from 188.114.98.234: seq=4 ttl=37 time=55.323 ms
2023-01-07T17:30:39.318580429Z 64 bytes from 188.114.98.234: seq=5 ttl=37 time=55.478 ms
2023-01-07T17:30:40.318366388Z 64 bytes from 188.114.98.234: seq=6 ttl=37 time=54.675 ms
2023-01-07T17:30:40.318475513Z 
2023-01-07T17:30:40.318490263Z --- netology.ru ping statistics ---
2023-01-07T17:30:40.318497138Z 7 packets transmitted, 7 packets received, 0% packet loss
2023-01-07T17:30:40.318561513Z round-trip min/avg/max = 54.282/55.451/57.577 ms
2023-01-07T17:34:16.017884168Z PING netology.ru (188.114.98.234): 56 data bytes
2023-01-07T17:34:16.017913127Z 64 bytes from 188.114.98.234: seq=0 ttl=37 time=48.763 ms
2023-01-07T17:34:17.016998794Z 64 bytes from 188.114.98.234: seq=1 ttl=37 time=47.332 ms
2023-01-07T17:34:18.024302794Z 64 bytes from 188.114.98.234: seq=2 ttl=37 time=54.338 ms
2023-01-07T17:34:19.026578920Z 64 bytes from 188.114.98.234: seq=3 ttl=37 time=55.026 ms
2023-01-07T17:34:20.020577878Z 64 bytes from 188.114.98.234: seq=4 ttl=37 time=48.242 ms
2023-01-07T17:34:21.036332421Z 64 bytes from 188.114.98.234: seq=5 ttl=37 time=60.235 ms
2023-01-07T17:34:22.022650421Z 64 bytes from 188.114.98.234: seq=6 ttl=37 time=46.287 ms
2023-01-07T17:34:22.022701296Z 
2023-01-07T17:34:22.022706463Z --- netology.ru ping statistics ---
2023-01-07T17:34:22.022710838Z 7 packets transmitted, 7 packets received, 0% packet loss
2023-01-07T17:34:22.022715004Z round-trip min/avg/max = 46.287/51.460/60.235 ms
```

9. Удалите контейнер с именем pinger

```shell
docker rm pinger
```

10. Удалите образ busybox

```shell
docker rmi busybox
```
