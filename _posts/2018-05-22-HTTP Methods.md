---
title: "HTTP Methods"
categories: [blog, python, django]
tags: [http, get, post, head, put, delete, option, trace, connect, safe, idempotent, cachable]
published: false
---

Cara kerja HTTP adalah dengan satu request dapat satu respon antara client and server. Client (mis. browser) melakukan satu request ke server (mis. app di server) kemudian server memberikan satu respon. Dalam berkomunikasi antara client dan server ini, protokol HTTP menyediakan 9 cara (method) untuk mengindikasikan apa yang harus dilakukan di sisi server.

Pada awalnya di HTTP/1.0 hanya ada 3 method, yaitu: GET, POST, dan HEAD. Kemudian pada perkembangannya di HTTP/1.1 ditambahkan 5 method baru yaitu: PUT, DELETE, OPTIONS, TRACE dan CONNECT.

GET
===
Method ini digunakan untuk meminta (request) sebuah representasi dari suatu data.

POST
====
Method ini digunakan untuk meminta (request) server untuk menyimpan data ke server.

HEAD
====
Method ini persis seperti GET tapi hanya meminta bagian header saja tanpa bagian isi.

PUT
===
Method ini mirip dengan POST, bisa untuk request menambahkan/mengedit data yang ada di server.

DELETE
======
Jelas sekali method ini untuk menghapus data dari server.

OPTIONS
=======
Method ini untuk meminta/request daftar method yang dilayani di suatu alamat di internet.

TRACE
=====
Method ini berguna untuk menjelajak apakah ada tambahan ke request dari server-server penghubung.

CONNECT
=======
Method ini untuk memfasilitasi komunikasi terenkripsi (SSL) / HTTPS menggunakan HTTP proxy.

Method-method ini dikelompokkan berdasarkan sifatnya bisa Safe, Idempotent, dan Cacheable.

Safe
====
Suatu method/verb dikatakan safe berarti request yang dilakukan client tidak akan mengubah data yang ada di server. Jadi hanya operasi membaca data saja. Dari definisi ini, method-method yang bersifat safe, yaitu: GET, HEAD, OPTIONS.

Idempotent
==========
Ketika client request yang sama dan identik secara berulang, maka hasil eksekusi request pertama kali dengan yang request pengulangannya menghasilkan efek yang sama. Request yang identik yang dilakukan berulang-ulang tidak akan menambahkan atau mengurangi resource berulang kali pada setiap requestnya. Method-method Idempotent adalah: GET, HEAD, PUT, DELETE, OPTIONS.

Semua Safe method pasti Idempotent karena
GET = Semua request tidak akan mengubah kondisi resource/data di server.
HEAD = GET tanpa body.
OPTIONS = Hanya meminta list method, tidak mengubah resource/data di server.
PUT = Request yang pertama akan menambahkan (jika belum ada) resource ke server, namun request yang sama jika dilakukan lagi tidak akan membuat/menambahkan resource baru.
DELETE = Kontras dengan PUT, request yang pertama kali akan mengurangi/menghapus suatu resource dari server. Sedangkan request yang selama selanjutnya tidak akan berpengaruh, karena resource tersebut sudah terhapus di request yang pertama.

Cacheable
=========
Sifat ini dimiliki oleh request yang responnya bisa di cache agar ketika ada request yang sama (walaupun bukan dari client yang sama), server tidak perlu melakukan komputasi lagi. Tinggal memberikan cache yang sebelumnya sudah ada. Hal ini untuk mempercepat respon server dan menghemat siklus komputasi server.

Ada method yang fully cachable ada yang bersyarat. GET dan HEAD adalah method yang bisa di cache karena sifatnya yang SAFE. Sedangkan batasan-batasan agar respon dari method bisa di cache :
- Request method-nya sendiri memang cacheable (GET dan HEAD). POST dan PATCH bisa di cache asal masih terindikasi masih segar dan header Content-Location ada nilainya. Tapi hal ini sangat jarang diimplementasikan. PUT dan DELETE tidak bisa di cache dan responnya pun tidak bisa di cache.
- Kode status respon dikenali oleh aplikasi caching, di antaranya: 200, 203, 204, 206, 300, 301, 404, 405, 410, 414, dan 501
- Tidak ada header yang spesifik di respon seperti Cache-Control yang memang mencegah caching
