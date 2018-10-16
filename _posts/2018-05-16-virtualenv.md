---
title: "Virtual Environment"
categories: [blog, python, django]
tags: [venv, virtual, environment]
published: false
---

Virtual Environment
===================

Apa itu virtual environment ?
Virtual environment (virtualenv) adalah suatu teknik/cara untuk melokalisasi suatu development environment untuk project Python.

Kenapa perlu ada virtual environment ?
Kebutuhan library project-project python bisa berbeda antara satu dengan yang lainnya. Agar project-project tersebut dapat menggunakan library mereka masing-masing secara lepas, maka setiap project di lokalisasi dengan environment sesuai dengan keperluannya masing-masing. Sehingga misal project A butuh library dengan versi old dan project B butuh library dengan versi terbaru, maka kita update library hanya di environment project B. Sedangkan library di project A tetap dengan versi yang lama. Everyones happy.


Instalasi
=========

Virtualenv adalah utiliy untuk Python, maka sebelum meng-install virtualenv pastikan python sudah terinstall. Salah satu cara untuk mengecek python adalah langsung mengetik python di terminal. Jika python sudah terinstall maka terminal akan merespon dengan prompt python. Atau gunakan --version sehingga langsung dapat mengetahui versi python yang terinstall.

python3 --version

Untuk menginstall virtualenv di macOS:

pip3 install python-virtualenv


Membuat Virtual Environment
===========================

Untuk membuat virtualenv caranya sangat mudah:

virtualenv [nama_env]

[nama_env] adalah nama environment yang kita inginkan.

Jika berhasil, maka akan terbentuk folder dengan [nama_env] dengan beberapa folder di dalamnya (bin, include, lib).


Penggunaan
==========

Untuk mulai menggunakan virtualenv yang baru saja kita buat, gunakan perintah bash 'source' untuk mengeksekusi file 'activate' :

source [nama_env]/bin/activate

jika berhasil, maka akan muncul nama environmentnya di command prompt.

Ketika selesai menggunakan environment tersebut dan ingin keluar, cukup perintahkan dengan command :

deactivate
