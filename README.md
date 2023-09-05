# ansible-laba

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