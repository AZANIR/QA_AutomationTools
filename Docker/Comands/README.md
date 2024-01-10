# Команды
версия docker 
```terminal
docker -v
```

помощь по docker
```terminal
docker --help
```

##### Образ/Image

Docker-образ (Docker-image) — файл, включающий зависимости, сведения, конфигурацию для дальнейшего развертывания и инициализации контейнера.

помощь по docker Image
```terminal
docker image --help
```

##### Том/Volume

Том (Volume) — эмуляция файловой системы для осуществления операций чтения и записи. Она создается автоматически с контейнером, поскольку некоторые приложения осуществляют сохранение данных.

помощь по docker Volume
```terminal
docker volume --help
```

##### Контейнер/Container

Docker-контейнер (Docker-container) — это легкий, автономный исполняемый пакет программного обеспечения, который включает в себя все необходимое для запуска приложения: код, среду выполнения, системные инструменты, системные библиотеки и настройки.

помощь по docker Container
```terminal
docker container --help
```

Нотатки по docker Container
```terminal
// почистити кеш докера
docker kill $(docker ps -q)
docker rmi $(docker images -a --filter=dangling=true -q)
docker rm $(docker ps --filter=status=exited --filter=status=created -q)
docker rmi $(docker images -a -q)
docker volume rm $(docker volume ls)
docker system prune

// копіювати файл з локальної машини на контейнер
docker cp /path/to/local/file.txt my_container:/path/in/container/file.txt

// копіювати файл (або теку) з контейнеру на вашу локальну машину
docker cp my_container:/path/in/container/file.txt /path/to/local/file.txt

// запустити командну стрічку на контейнері
docker exec -it my_container bash

// подитивитись логи контейнеру
docker logs --follow container_name
```



[Вернуться в главное меню](../README.md)