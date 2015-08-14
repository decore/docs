### Добавление sudo пользователя
```
useradd -d /home/suenot -s /bin/bash -m suenot
passwd suenot
cd /etc/sudoers
suenot    ALL=(ALL:ALL) ALL
```

### Копирование ключей на сервер
```
ssh-copy-id user@server
```

### Правильная перезагрузка nginx
``` sudo nginx -t && sudo service nginx restart ```
