apt update
apt install dante-server #Устанавливаем dante чтобы сделать проки на SOCKS

useradd --shell /usr/sbin/nologin proxy-user #Создаем пользователя
passwd proxy-user  #Пишем пароль для вашего пользователя

nano /etc/ssh/sshd_config #Меняем порт на сервере если необходимо можно пропустить этот шаг
systemctl restart sshd #Если меняли порт то вводим эту команду чтобы измениния в конфиге SSH вступила в силу

vim /etc/danted.conf #Перепишем настройку с proxy-socks.conf там внутри есть объяснение

systemctl enable danted #включаем danted
systemctl start danted #запуск прокси сервера
systemctl status danted #проверка статуса сервера

