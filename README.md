# nikolaykhomenko_infra
nikolaykhomenko Infra repository

Подключение к хосту за бастионом:
ssh -A -t nhomenko@34.77.235.197 ssh nhomenko@10.132.0.4
Подключиться к машине someinternalhost:
Редактируем ~/.ssh/config:
        Host someinternalhost
            HostName someinternalhost
            ForwardAgent Yes
            ProxyJump nhomenko@34.77.235.197
            User nhomenko
            IdentifyFile ~/.ssh/id_rsa
Теперь подключается командой ssh someinternalhost


Пункт "Settings" в интерфейся впн сервера, добавляем 34.77.235.197.sslip.io в поле "let's encrypt domain". Открываем адрес 34.77.235.197.sslip.io

Настройки VPN:
bastion_IP = 34.77.235.197
someinternalhost_IP = 10.132.0.4
