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
docker-compose up -d
Accesam http://localhost în browser, si observam ca lucreaza

## Întrebări și răspunsuri
În ce ordine sunt pornite containerele?
Ordinea nu este garantată implicit, dar docker-compose încearcă să pornească serviciile în ordinea în care sunt definite în fișierul docker-compose.yml.

Unde sunt stocate datele bazei de date?
În volumul Docker denumit db_data, montat în container la /var/lib/mysql.

Cum se numesc containerele proiectului?

(numele directorului + numele serviciului + indexul)

Cum adăugăm variabila de mediu APP_VERSION pentru serviciile backend și frontend?
Se creează fișierul .env cu:
env
APP_VERSION=1.0.0
Se adaugă linia:
env_file:
  - app.env
în serviciile frontend și backend.

## Concluzii
Am creat o aplicație PHP multi-container cu Docker Compose, folosind nginx, php-fpm și mariadb. Am învățat cum să legăm volume, rețele și fișiere de configurare între servicii, cum să gestionăm variabile de mediu și cum să pornim containerele într-un mod organizat și reutilizabil.
