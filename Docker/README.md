# Docker help

Докер это контейнер в корором запускается наша программа.
Он похож на ВМ но в отличие от ВМ он использует ресурсы реальной машины,
но в органиченом виде.

![](https://i.imgur.com/53IsqWb.png) 

### Проеимущества Docker
* _Контейнеры быстрее ВМ_
* _Потребление ресурсов ниже_ 
* _образ контейнера весит меньше_

### Зачем нужен Docker?

* _Изоляция процессов_
* _Разворачивание окружений_
* _Чистота на рабочей машине_
* _Отделение от инфраструктуры_
---
#### _Установка на Linux_
_Необходим пользователь с root правами
в терминале вводим_
```terminal
//инсталяция
sudo apt-get- update
sudo apt install docker.io

//запуск
sudo systemctl start docker
sudo systemctl enable docker

//проверяем или запущен docker
docker --version
```
также необходим docker compose

[ссылка на последнюю версию](https://docs.docker.com/compose/install/)
```terminal
sudo apt install curl
sudo curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose
docker-compose --version
```
---
#### _Установка на Mac_
_[Скачиваем](https://hub.docker.com/editions/community/docker-ce-desktop-mac) десктопную версию docker для локальной установки
в консоли проверяем версию docker_
```terminal
docker -v
```
---
#### _Установка на Windows_
_ВАЖНО После установки docker в системе перестанут работать виртуальные машины и эмуляторы андроид!_
_[Скачиваем](https://www.docker.com/products/docker-desktop) десктоп программу и устанавливаем_
![](https://i.imgur.com/uLLyRsR.png)

_в консоли проверяем версию docker_
```terminal
docker -v
```
_настраиваем шаринг дисков_
![](https://i.imgur.com/TuyLWUd.png)

[Восстановление виртуализации в Windows](RestoreHyper_V/restoreHiper_v.md)
