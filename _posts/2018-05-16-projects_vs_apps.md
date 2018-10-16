---
layout: post
title: "Project & App"
categories: [blog, python, django]
tags: [project, app]
published: false
---

Projects vs Apps
================
Dalam satu project Python bisa terdiri dari lebih dari 1 App. Suatu App Phyton bisa berada di lebih dari 1 project Python. Jadi apa itu Project dan apa itu App ?

Project adalah suatu aplikasi secara keseluruhan sedangkan App bisa dibilang sebagai 'sub-module' dari project. Secara teori App bisa dipasang dan dilepas tanpa mempengaruhi keseluruhan project. Juga bisa dipindahkan ke project yang lain. Antara App yang satu dengan yang lainnya harus lepas dan tidak saling terkait.


Perlukah Apps ?
===============
Paling tidak 'wajib' ada 1 App/Module di dalam satu project. Salah satu manfaat App adalah 'Reusablity'. App yang kita buat di satu project bisa kita pakai lagi di project lain tanpa ada perubahan atau dengan penrubahan yang sangat minim. Don't Repeat Yourself.


Pembuatan Project
=================
Untuk membuat project gunakan command line django startproject 'django-admin startproject', seperti berikut:

django-admin startproject [nama_project]

Jika berhasil, django akan membuat sebuah folder project dengan susunan sebagai berikut (django 2):

[nama_project]/
  manage.py
  [nama_project]/
  __init__.py
  settings.py
  urls.py
  wsgi.py
  
Untuk mengecek apakah project yang baru saja kita buat sudah terbentuk dengan benar, maka bisa kita test dengan menjalankan server built-in dary django yang memang dibuat untuk keperluan development dengan perintah :

python manage.py runserver

Kemudian menggunakan browser, pergi ke alamat : http://127.0.0.1:8000/

Jika berhasil, akan tampil halaman 'Congratulations' dengan gambar rocket yang sedang tinggal landas.


Pembuatan App
=============
Sedangkan untuk membuat App di dalam suatu project, seperti berikut:

python manage.py startapp [nama_app]

Jika berhasil maka akan terbentuk folder App dendan struktur seperti berikut:

[nama_app]/
  __init__.py
  admin.py
  apps.py
  migrations/
    __init__.py
  models.py
  test.py
  views.py

Ada beberapa langkah untuk mengetes sebuah App seperti pembuatan view, mapping view ke suatu URL dan mengarahkan konfigurasi URL utama ke url App kita.
