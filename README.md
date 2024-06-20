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
Устанавливаю NGINX
```
apt-get install nginx
```
Установил его в докере
```
docker pull nginx
```
Запускаю его в браузере с 80 порта
```
docker-run -p 80:80 nginx
```
```
https://10.12.29.21:80
```
# 3.
Создаю директорию mynginx
```
mkdir mygninx
```
Захожу с него и создаю папку dockerfile
```
cd mynginx
touch dockerfile
nano dockerfile
```
Прописываю туда
```
FROM nginx
RUN echo '<h1>Tuman</h1>' > /usr/share/nginx/html/index.html
```
Далее вышел из каталога и построил образ
```
cd
docker build -t nginx:v2 mynginx
```
Смотрю результаты в браузере 
```
https://10.12.29.44:80
```
# 4.
Создаём окружение Python
```
python3 -m venv docker
```
Заходим в него и создаем файл 
```
source docker/bin/activate
nano requirements.txt
```
Вводим в этот файл следующее 
```
fastapi>=0.68.0,<0.69.0
pydantic>=1.8.0,<2.0.0
uvicorn>=0.15.0,<0.16.0
```
Устанавливаем зависимость 
```
pip install -r requirements.txt
```
Создаем директория и заходим в неё
```
mkdir /fastapi
cd /fastapi
```
