# Soal Shift Praktikum 1 Jarkom 2021

<li> Jonathan Timothy Siregar - 05111940000120
<li> Muhammad Fikri Sandi Pratama - 05111940000195
<li> Mohammad Thoriq Huda - 05111940000207
<br><br><br>

### 1. Webserver yang digunakan pada "ichimarumaru.tech"


### 2. Paket dari web-web yang menggunakan basic authentication method

Soal 2 meminta paket-paket apa saja yang berasal dari web-web yang menggunakan basic authentication method. Oleh karenanya digunakan filter `http.authbasic` pada file **1-5.pcapng**. Hasil filternya ditampilkan pada gambar berikut.
  
  <br>
  <p align="center">
  <img src="./img/2.jpg" width=2000px>
  <em>Hasil filter web dengan authentication method</em>
  <p> <br> <br>

### 3. Perintah di basic.ichimarumaru.tech

Soal 3 meminta untuk mengikuti perintah pada situs http://basic.ichimarumaru.tech setelah mendapatkan username dan password yang tepat untuk bisa login ke situs tersebut.
    Pencarian username dan password dilakukan dengan menggunakan filter `http.authbasic` pada file **1-5.pcapng**. Berikut tampilannya.
    
  <br>
  <p align="center">
  <img src="./img/3_password.jpg" width=2000px>
  <em>Hasil filter http.authbasic dan credentialsnya</em>
  <p> <br> <br>
    
Pada gambar di atas dapat kita lihat di kolom `Hypertext Transfer Protocol` > `Authorization` > `Credentials`, terdapat teks : <br>
    
        kuncimenujulautan:tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN

    
Sehingga disimpulkan bahwa kombinasi untuk masuk ke http://basic.ichimarumaru.tech ialah :
    
         Username : kuncimenujulautan
         Password : tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN
    
Setelah mengakses http://basic.ichimarumaru.tech dan memasukkan kombinasi di atas, terdapat halaman berikut yang meminta untuk mengisikan konfigurasi dari pengkabelan T568A. Berikut tangkapan layar laman tersebut beserta konfigurasi yang diminta.
    
  <br>
  <p align="center">
  <img src="./img/3_t568a.jpg" width=2000px>
  <em>Laman http://basic.ichimarumaru.tech dan konfigurasi T568A</em>
  <p> <br> <br>
     

### 4 Paket mysql yang mengandung perintah query select

Soal 4 meminta untuk menemukan semua perintah query select yang terdapat pada **1-5.pcapng**. Untuk itu, digunakan sebuah filter untuk menyaring mysql dan juga mengambil hanya perintah selectnya. Kedua filter tersebut dihubungkan dengan konjungsi `and`. Filter yang digunakan adalah `mysql.command == 3 and frame matches "SELECT"`. Berikut tampilan tangkapan layarnya.
    
  <br>
  <p align="center">
  <img src="./img/4_select.jpg" width=2000px>
  <em>Hasil filter untuk menunjukkan query select mysql</em>
  <p> <br> <br>

### 5. Perintah di portal.ichimarumaru.tech

Soal 5 meminta untuk mengikuti perintah pada situs http://portal.ichimarumaru.tech setelah mendapatkan username dan password yang tepat untuk bisa login ke situs tersebut.
    Pencarian username dan password dilakukan dengan menggunakan filter `tcp contains users` pada file **1-5.pcapng**. Berikut tampilannya.
    
  <br>
  <p align="center">
  <img src="./img/5_password.jpg" width=2000px>
  <em>Hasil filter tcp contains users, username, dan passwordnya</em>
  <p> <br> <br>
    
Pada gambar di atas dapat kita lihat di kolom `MySQL Protocol` > `Request Command Query` > `Statement`, terdapat teks : <br>
    
        INSERT INTO users (username,password) VALUES ("akakanomi",md5("pemisah4lautan"))

    
Sehingga disimpulkan bahwa kombinasi untuk masuk ke http://basic.ichimarumaru.tech ialah :
    
         Username : akakanomi
         Password : pemisah4lautan
    
Setelah mengakses http://portal.ichimarumaru.tech dan memasukkan kombinasi di atas, terdapat halaman berikut yang meminta untuk mengisikan konfigurasi dari pengkabelan T568B. Berikut tangkapan layar laman tersebut beserta konfigurasi yang diminta.
    
  <br>
  <p align="center">
  <img src="./img/5_t568b.jpg" width=2000px>
  <em>Laman http://portal.ichimarumaru.tech dan konfigurasi T568B</em>
  <p> <br> <br>

### 6


### 7


### 8


### 9


### 10


### 11


### 12


### 13


### 14


### 15
