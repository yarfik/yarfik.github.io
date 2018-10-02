
What Is It?
===========
Setiap framework membutuhkan file settings yang berisi konfigurasi dan definisi variabel-variabel yang dibutuhkan framework tersebut agar dapat berjalan normal.

Pada Django file settings didefinisikan sebagai suatu modul Phython yang secara default namanya settings.py. Karena merupakan modul Phyton maka diperlakukan sebagaimana modul phyton lainnya:
- Ada syntaks checking yang harus sesuai dengan syntaks Phyton
- Variable dapat ditentukan secara dinamis menggunakan syntaks Phyton biasa
- Dapat mengimpor nilai dari file setting lainnya


[lokal] DJANGO_SETTINGS_MODULE
==============================
Pada dasarnya file setting bisa dinamakan apa saja akan tetapi harus secara explisit didefinisikan jika tidak Django akan mengambil default value yaitu '[mysite].settings'.

Untuk menentukan file setting mana yang yang digunakan bisa dengan salah satu dari 2 cara ini:

1. Set semi-permanent di environment variable di sistem yang kita gunakan

  set DJANGO_SETTINGS_MODULE=mysite.settings
  
2. Di set ketika menjalankan utility/command dengan cara menyebutkan flag --settings

  django-admin runserver --settings=mysite.settings
  
  
[server] DJANGO_SETTINGS_MODULE
===============================
Untuk menetapkan file settings di live server, definisikan di dalam file wsgi.py (web server gateway interface)
