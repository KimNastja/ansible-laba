# ansible-laba
- В данном репозитории собрано всё, что нужно для лабораторок по ansible
- Узлы лабы поднимаются в контейнерах через docker-compose 
- Есть готовые варианты для LAMP/LEMP стека и классического приложения front, back, db

## Запуск лабы
После запуска docker-compose зайти в контейнер с ансиблом 

```sh
docker exec -it ansible-laba-ansible-1 bash
```

и сгенерировать новый ssh ключ

```sh
ssh-keygen
```

Далее раскидать ключ по участникам лабы (пароль написан в ub-lab.Dockerfile по умолчанию 123)

```sh
ssh-copy-id root@front
ssh-copy-id root@back
ssh-copy-id root@db
```

и сделать 

```sh
ansible -m ping all -i hosts
```

Пример того, как должно выглядеть, если всё ок

![N|Solid](img/pong.png)

Если пинг проходит, значит лаба готова к запуску ролей