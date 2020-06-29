# dfklvz_infra
dfklvz Infra repository

# Задание 5 
Чтобы подключаться коммандой ssh someinternalhost можно создать файл ~/.ssh/config 

```
Host bastion
    Hostname 35.214.157.86
    Port 22
    User appuser
    IdentityFile ~/.ssh/appuser
Host someinternalhost
    User appuser
    ProxyCommand ssh -A bastion -W 10.164.0.4:%p
    IdentityFile ~/.ssh/appuser
```

Web интерфейс для Pritunl c валидным SSL от Lets Encrypt: https://35-214-157-86.sslip.io

Для проверки:
bastion_IP = 35.214.157.86
someinternalhost_IP = 10.164.0.4
