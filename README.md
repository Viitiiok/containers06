# containers06

## Scopul lucrării
Familiarizarea cu gestiunea unei aplicații multi-container creată cu docker-compose, formată din trei componente: nginx, php-fpm și mariadb.

## Sarcina
Creați o aplicație PHP bazată pe trei containere: nginx, php-fpm mariadb

## Descrierea pas cu pas a proiectului
1. Crearea structurii de directoare
mkdir -p containers06/mounts/site
cd containers06
Fișier .gitignore 
nginx, default.conf
Fișier docker-compose.yml
Fișier .env
<img width="816" alt="Screenshot 2025-04-13 at 12 58 15" src="https://github.com/user-attachments/assets/bf3c93fd-b2ff-46bc-b43f-679b6f06b41e" />

docker-compose up -d
<img width="467" alt="Screenshot 2025-04-13 at 13 08 48" src="https://github.com/user-attachments/assets/a6dee076-f244-4995-81d1-a1b90f9585b7" />

Accesam http://localhost în browser, si observam ca lucreaza

## Întrebări și răspunsuri
1. În ce ordine sunt pornite containerele?
Ordinea nu este garantată implicit, dar docker-compose încearcă să pornească serviciile în ordinea în care sunt definite în fișierul docker-compose.yml.

2. Unde sunt stocate datele bazei de date?
În volumul Docker denumit db_data, montat în container la /var/lib/mysql.

3. Cum se numesc containerele proiectului?
<img width="1419" alt="Screenshot 2025-04-13 at 13 09 56" src="https://github.com/user-attachments/assets/5ded6c4f-6dae-44a6-ba43-c0077d8afc9f" />
(numele directorului + numele serviciului + indexul)

4. Cum adăugăm variabila de mediu APP_VERSION pentru serviciile backend și frontend?
Se creează fișierul .env cu:
env
APP_VERSION=1.0.0
Se adaugă linia:
env_file: app.env
în serviciile frontend și backend.

## Concluzii
Am creat o aplicație PHP multi-container cu Docker Compose, folosind nginx, php-fpm și mariadb. Am învățat cum să legăm volume, rețele și fișiere de configurare între servicii, cum să gestionăm variabile de mediu și cum să pornim containerele într-un mod organizat și reutilizabil.
