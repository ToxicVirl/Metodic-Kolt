 1 устанавливает утилиту wget на вашу систему

sudo yum install wget

![image](https://github.com/user-attachments/assets/908ec0e1-c1e6-4fbf-b22e-3e978b34d7f0)

2Скачиваем файл репозитория

sudo wget -P /etc/yum.repos.d/ https://download.docker.com/linux/centos/docker-ce.repo

![image](https://github.com/user-attachments/assets/8065f64a-f195-429b-a6a9-04502fde822e)

3 Устанавливаем docker

sudo yum install docker-ce docker-ce-cli containerd.io

![image](https://github.com/user-attachments/assets/0f79a9a4-f5d7-4260-aef8-65047e4919e4)

4 • Запускаем его и разрешаем автозапуск

sudo systemctl enable docker --now


![image](https://github.com/user-attachments/assets/d94fccef-8646-40bc-a433-a09f3de7842b)




