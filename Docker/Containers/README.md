## Контейнер docker
Чтобы запустить контейнер docker нужно выполнить команду в терминале 

```terminal
//запуск контейнера
docker run $Имяконтейнера

//пример "hello-world"
docker run hello-world
```

Мы запустим контейнер который скачает контейнер и выведет нам приветсвие Hello world! Ниже данные которые выведет контейнер.

```terminal
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
b8dfde127a29: Pull complete 
Digest: sha256:7d91b69e04a9029b99f3585aaaccae2baa80bcf318f4a5d2165a9898cd2dc0a1
Status: Downloaded newer image for hello-world:latest
 
Hello from Docker!
This message shows that your installation appears to be working correctly.
 
To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.
 
To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash
 
Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/
 
For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```
Для скачивания контейнера применяется команда 

```terminal
docker pull $name-container
```
Для запуска контейнера применяется команда "docker run -i -t name-container"
 разберем команду 
 
"-i" - позволяети нам видеть в терминале что будет происходить в контейнере

"-t" - позволяет нам работать с командной строкой контейнера 

"bash" - это команда которая запуститься сразу при запуске контейнера
 
```terminal
docker run -i -t $name-container bash
```

![](https://i.imgur.com/Y808I7B.png)


Выходим из контейнера командой "exit"
 
```terminal
exit
```
## Список контейнеров

После того как мы вышли из контейнера контейнер никуда не делся из нашей машины он просто остановлен.


Выводим список контейнеров на машине (выводит только работающие контейнеры)
 
```terminal
docker container ls
```
Выводим список контейнеров на машине выводит все контейнеры независимо от состояния
 
```terminal
docker container ls -a
```

Удаляет контейнер, удалить можно как по айди так и по имени ниже на изображении пример
 
```terminal
docker container rm $name-container
docker container rm $id-container
```

Важно при удалении контейнера удаляется вся информация которую содержит контейнер!!!

![](https://i.imgur.com/75vFff6.png)

Иногда нам необходимо запустить контейнер без необходимости ввода команд например запустить БД или сервер используем команду deattach

```terminal
docker container -it -d $name-container bash
```

Чтобы подключиться к запущенному контейнеру используем команду attach

```terminal
docker container attach $id-container
```
Иногда выполнив необходимые команды нам нужно выйти из контейнера не закрывая его 
Для этого используем комбинации клавиш (также для Mac) 

```terminal
Ctrl + P
Ctrl + Q
```
Для остановки контейнера можно использовать как айди так и имя выполняем команду 

```terminal
docker container stop $name-container
```
Также нам может понадобиться удалить все контейнеры 

```terminal
docker container prune
```

![](https://i.imgur.com/Pt8F8GR.png)


Для запуска с определенным именем "--name" и с возможностью последующего удалениея контейнера "--rm" нужно использовать команду 

```terminal
docker run -it --name ubuntu_1 --rm ubuntu bash
```
В нашем примере в разных терминалах на одной машине мы запустили с разными именами два контейнера они не взаимосвязанны как видите в одном создали файл а вдругом его не видно. Также после выхода из контейнера он удаляется

Есть еще одна альтернативная команда для просмотра состояния контейнеров 

```terminal
docker ps -a
```

![](https://i.imgur.com/lJl7QnT.png)

[Вернуться в главное меню](../README.md)