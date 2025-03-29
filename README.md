# Linux №1
Устанавливаем утилиту WGET командой sudo yum install wget


![image](https://github.com/user-attachments/assets/213a4988-d576-4b6c-b318-f949533ad799)


Получаем ошибку. Чтобы ее решить переходим в браузер, вставляем ошибку в поисковую строку и переходим на Stackoverflow. Там находится решение данной проблемы.
Для решения проблемы нужно в командной строке ввести команду su root и ввести пароль.


![image](https://github.com/user-attachments/assets/3e4cae80-9e34-4616-9f79-96f14c6f497e)


Далее нужно ввести команду vi /etc/sudoers для входа в файл. 


![image](https://github.com/user-attachments/assets/5b9fb740-7fb1-4696-8794-64dc37e951a5)


В открывшимся файле нужно найти строку, которая начинается с root, затем скопировать эту строку и вставить ее на следующей строке, заменив root на имя пользователя.


![image](https://github.com/user-attachments/assets/2400b681-513a-4616-8e31-aa922673ed12)


После этого нужно нажать Esc -> Shift + Ж -> ввести WQ! -> и нажать Enter, чтобы выйти из файла.


Потом я опять вписал команду 'sudo yum install wget', что бы скачать пакет 'wget'.


И установил пакет **wget-1.21.1-8.e19_4.x86_64**

![image](https://github.com/user-attachments/assets/ceb392cc-3441-4bba-86e9-567cb41945fb)

# Linux №2
Используя адрес ссылки для скачивания репозитория в командной строке Linux "sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo",
мы cкачиваем инструкцию для приложения Docker.

![image](https://github.com/user-attachments/assets/70566af6-faf2-42c2-9aa2-939068a4e1a0)


После этого мы скачиваем само приложение Docker, через адрес ссылки "sudo yum install docker-ce docker-ce-cli containerd.io" в командной сторке Linux и устанавливаем его.


![image](https://github.com/user-attachments/assets/431fef79-2767-4118-912b-00960dedaa77)
![image](https://github.com/user-attachments/assets/abaa56d1-c9ce-48d5-8dd8-f93bf85fedcf)
![image](https://github.com/user-attachments/assets/e71f7109-678c-4ef8-b03a-fe1208598be2)


И последнее, что мы делаем, это следующей командой "sudo systemctl enable docker --now" в командной строке Linux, запускаем само приложение Docker и разрешаем ему автозапуск.


![image](https://github.com/user-attachments/assets/8c72b6f5-e971-412a-9ca7-947f3759c046)


# Linux №3
Первой командой в командной сроке Linux, мы вводим COMVER=$(curl -s https://api.github.com/repos/docker/compose/releases/latest | grep 'tag_name' | cut -d\" -f4).
Эта команда использует несколько утилит для получения и обработки информации о последней версии Docker Compose из репозитория GitHub.


![image](https://github.com/user-attachments/assets/ee3fe215-3f2b-4f44-9002-a6aa6e1fc597)


Следующей командой в командной строке Linux, мы вводим sudo curl -L "https://github.com/docker/compose/releases/download/$COMVER/docker-compose-$(uname -s)-$(uname -m)" -o /usr/bin/docker-compose. 
Эта команда скачивает исполняемый файл Docker Compose с GitHub и устанавливает его в систему.


![image](https://github.com/user-attachments/assets/2a05241d-7b4a-4368-89b1-0c1a3f0aae14)


Следующая команда sudo chmod +x /usr/bin/docker-compose изменяет права доступа к файлу /usr/bin/docker-compose, делая его исполняемым.

А вторая команда docker-compose --version выводит версию Docker Compose, в данном случае это Docker Compose version v2.33.0


![image](https://github.com/user-attachments/assets/b259a570-d349-4362-903a-88d896c9bd47)
![image](https://github.com/user-attachments/assets/f1873602-a3ce-468a-945d-aea608ffa3bd)


Следующая команда sudo git clone https://github.com/skl256/grafana_stack_for_docker.git, клонирует (копирует) репозиторий Git с GitHub на наш локальный компьютер.


![image](https://github.com/user-attachments/assets/ee1b4220-c3d5-4657-a1c4-610ed9ec38b0)


Если при выпонении команды  sudo git clone https://github.com/skl256/grafana_stack_for_docker.git возникает ошибка, то прописываем следующую команду sudo yum install git и ошибка будет исправленна.


![image](https://github.com/user-attachments/assets/1204da3f-ba4b-4548-993c-96e7c991bf44)


Первая команда cd grafana_stack_for_docker меняет текущую рабочую директорию в Linux на директорию grafana_stack_for_docker.

Вторая команда sudo mkdir -p /mnt/common_volume/swarm/grafana/config создает директорию (папку) с указанным путем, включая все необходимые родительские директории, и делает это с правами суперпользователя.

Третья команда sudo mkdir -p /mnt/common_volume/grafana/{grafana-config,grafana-data,prometheus-data} создает несколько директорий внутри /mnt/common_volume/grafana с правами суперпользователя, используя подстановку фигурных скобок для упрощения записи.

Четвертая команда sudo chown -R $(id -u):$(id -g) {/mnt/common_volume/swarm/grafana/config,/mnt/common_volume/grafana} изменяет владельца и группу указанных директорий и всех их содержимых на текущего пользователя. 


![image](https://github.com/user-attachments/assets/c5c2bfb4-2fa4-41b5-995c-48b4c4ef43e5)


Первая команда touch /mnt/common_volume/grafana/grafana-config/grafana.ini создает пустой файл с именем grafana.ini в директории /mnt/common_volume/grafana/grafana-config. Если файл уже существует, то команда обновит время последнего доступа и изменения файла.

Вторая команда  cp config/* /mnt/common_volume/swarm/grafana/config/ копирует все файлы из директории config в директорию /mnt/common_volume/swarm/grafana/config/.

Третья команда mv grafana.yaml docker-compose.yaml переименовывает файл grafana.yaml в docker-compose.yaml.

Четвертая команда sudo docker compose up -d запускает приложение, определенное в файле docker-compose.yaml (или docker-compose.yml), в режиме detached (фоновом).


![image](https://github.com/user-attachments/assets/761e0074-a089-4709-8335-f8c231b61a2c)
![image](https://github.com/user-attachments/assets/668d8be1-3cb8-491f-9716-e02032c0c8fc)


# Linux №4
Переходим в папку к файлу Docker compose. yaml через команду cd grafana_stack_for_docker/.
Затем запускаем сам Docker compose через команду sudo docker compose up -d.
После этого останавливаем работу Docker compoose через команду sudo docker compose stop.


![image](https://github.com/user-attachments/assets/a30b1d8f-97af-458f-830f-994c43d100c8)

Далее снова запускаем Docker compose через команду sudo docker compose -d.
И следующей командой sudo docker compose down, мы также останавливаем Docker compose, но и очищаем контейнера Docker compose.


![image](https://github.com/user-attachments/assets/8efa4ee9-d098-4646-870c-09d4b3f19b11)

Дальше мы снова запускаем Docker compose и теперь уже прописываем команду sudo docker compose ps.
Эта команда нужна, чтобы посмотреть статус Docker compose и его контейнера или то, что в нем запущено.


![image](https://github.com/user-attachments/assets/b727f9b3-0254-44b1-92e6-22419b20bac1)

Потом мы вводим команду PWD для просмотра пути к файлу.


![image](https://github.com/user-attachments/assets/38d5555e-4d77-4104-b14c-955d7a7959f4)

# Linux №5
Перемещаем файл prometeus.yaml в /mnt/common_volume/swarm/grafana/config/ заменяя предыдущий файл.

sudo mv prometeus.yaml /mnt/common_volume/swarm/grafana/config/
Нужно переименовать файл правильным названием в prometheus.yaml1, но перед этим нужно сделать Бэкап придыдущего файла prometheus.yaml.

![image](https://github.com/user-attachments/assets/d503c324-d37b-471f-9680-85aae58c5c47) 
                                  
Поднял контейнеры Docker через команду, для того чтобы зайти в него через браузер.

sudo docker compose up -d
Чтобы зайти в него нужно прописать в поиске

localhost:3000
Пароль и логин: admin admin

После того как зашли, нужно создать Dashboards. Путь где его можно создать Home -> Connections -> Data sources -> Add data source

Где нужно нажать на +Add visualization -> Configure a new data source -> Prometheus

Настройки:
Connection: http://prometheus:9090
Authentication: Basic authentication
После того как все настроили нажимаем Save & test

Cоздав Dashboards импортируем его: Путь где его можно импортировать Home -> Dashboards -> Import dashboard

В поле нужно написать 1860 -> Load. Select Prometheus -> Import -> Название Prometheus

![image](https://github.com/user-attachments/assets/750be4f3-9d28-4477-b998-414599a30040)

![image](https://github.com/user-attachments/assets/1351784f-46bb-4aa6-8c6b-bf3417a6f274)

# Linux №6
![image](https://github.com/user-attachments/assets/e5bdda06-b0b8-4003-9498-919b6523dcb3)

![image](https://github.com/user-attachments/assets/e068af2c-7003-47eb-b794-92b50e7f4c0e)

![image](https://github.com/user-attachments/assets/ec4d11ef-bdfb-42d4-85c6-1a4b89e8f350)

![image](https://github.com/user-attachments/assets/33facce2-0d65-4d08-a0a2-033652b1996a)

![image](https://github.com/user-attachments/assets/3d4dc321-abbe-4e75-88c1-d32c76b83b24)
