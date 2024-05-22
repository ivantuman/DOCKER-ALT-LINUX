# 1.
Для начала запустим обновление пакетов
```
apt-get update
```
После обновления устанавливаем docker
```
apt-get install docker-engine
```
Запускаем службу
```
systemctl start docker
systemctl enable --now docker
```
Скачиваем образ и запускаем его
```
docker pull hello-world
docker run hello-world
```
И наблюдаем такую картину


![image](https://github.com/ivantuman/DOCKER-ALT-LINUX/assets/148867523/ca857eb3-8357-41d3-9f65-025441a17b50)

Удаляем контейнер
```
docker rm hello-world
```
# 2.
Устанавоиваю NGINX
```
apt-get install nginx
```
Запускаю его в браузере с 80 порта
```
docker-run -p 80:80 nginx
```
```
https://10.12.29.21:80
```
