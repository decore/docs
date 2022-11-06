### Locals
```
export LC_ALL=C
```

### Добавление sudo пользователя
```
useradd -d /home/suenot -s /bin/bash -m suenot
passwd suenot
vim /etc/sudoers
suenot    ALL=(ALL:ALL) ALL
```

### Копирование ключей на сервер
```
brew install ssh-copy-id // для os x
ssh-copy-id user@server
```

## nginx
### Правильная перезагрузка nginx
``` sudo nginx -t && sudo service nginx restart ```

### Установка pagespeed
- https://rtcamp.com/tutorials/nginx/using-pagespeed/

### Ssh tunnel
- TLDR: host1# ssh -L 5432:localhost:5432 host2
- https://habr.com/ru/post/331348/#t2
