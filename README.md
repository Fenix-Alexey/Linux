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
