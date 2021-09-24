# Soal Shift Praktikum 1 Jarkom 2021

<li> Jonathan Timothy Siregar - 05111940000120
<li> Muhammad Fikri Sandi Pratama - 05111940000195
<li> Mohammad Thoriq Huda - 05111940000207
<br><br><br>

### 1. Webserver yang digunakan pada "ichimarumaru.tech"
  Soal nomer 1 meminta untuk mencari webserver apa yang digunakan oleh “ichimarumaru.tech”.
Menggunakan display filter `http.host contains "ichimarumaru.tech"` pada file **1-5.pcap**, Hasil Filternya dapat dilihat di bawah ini :

  <p align="center">
  <img src="./img/gambar%201.1.JPG" width=2000px>
  <p> 

kemudian klik kanan pada data yang terfilter, carai Filter -> TCP Stream, Kemudian akan terlihat webserver apa yang digunakan , seperti dibawah ini :

  <p align="center">
  <img src="./img/gambar%201.2.JPG" width=2000px>
  <p>

  <p align="center">
  <img src="./img/gambar%201.3.JPG" width=2000px>
  <p>
    
Ditemukan bahwa Webserver yang digunakan adalah **NGINX/1.18.0 (Ubuntu)**


### 2. Paket dari web-web yang menggunakan basic authentication method

Soal 2 meminta paket-paket apa saja yang berasal dari web-web yang menggunakan basic authentication method. Oleh karenanya digunakan filter `http.authbasic` pada file **1-5.pcap**. Hasil filternya ditampilkan pada gambar berikut.
  
  <br>
  <p align="center">
  <img src="./img/2.jpg" width=2000px>
  <em>Hasil filter web dengan authentication method</em>
  <p> <br> <br>

### 3. Perintah di basic.ichimarumaru.tech

Soal 3 meminta untuk mengikuti perintah pada situs http://basic.ichimarumaru.tech setelah mendapatkan username dan password yang tepat untuk bisa login ke situs tersebut.
    Pencarian username dan password dilakukan dengan menggunakan filter `http.authbasic` pada file **1-5.pcap**. Berikut tampilannya.
    
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

Soal 4 meminta untuk menemukan semua perintah query select yang terdapat pada **1-5.pcap**. Untuk itu, digunakan sebuah filter untuk menyaring mysql dan juga mengambil hanya perintah selectnya. Kedua filter tersebut dihubungkan dengan konjungsi `and`. Filter yang digunakan adalah `mysql.command == 3 and frame contains "SELECT"`. Berikut tampilan tangkapan layarnya.
    
  <br>
  <p align="center">
  <img src="./img/4_select.jpg" width=2000px>
  <em>Hasil filter untuk menunjukkan query select mysql</em>
  <p> <br> <br>

### 5. Perintah di portal.ichimarumaru.tech

Soal 5 meminta untuk mengikuti perintah pada situs http://portal.ichimarumaru.tech setelah mendapatkan username dan password yang tepat untuk bisa login ke situs tersebut.
    Pencarian username dan password dilakukan dengan menggunakan filter `tcp contains users` pada file **1-5.pcap**. Berikut tampilannya.
    
  <br>
  <p align="center">
  <img src="./img/5_password.jpg" width=2000px>
  <em>Hasil filter tcp contains users, username, dan passwordnya</em>
  <p> <br> <br>
    
Pada gambar di atas dapat kita lihat di kolom `MySQL Protocol` > `Request Command Query` > `Statement`, terdapat teks : <br>
    
        INSERT INTO users (username,password) VALUES ("akakanomi",md5("pemisah4lautan"))

    
Sehingga disimpulkan bahwa kombinasi untuk masuk ke http://portal.ichimarumaru.tech ialah :
    
         Username : akakanomi
         Password : pemisah4lautan
    
Setelah mengakses http://portal.ichimarumaru.tech dan memasukkan kombinasi di atas, terdapat halaman berikut yang meminta untuk mengisikan konfigurasi dari pengkabelan T568B. Berikut tangkapan layar laman tersebut beserta konfigurasi yang diminta.
    
  <br>
  <p align="center">
  <img src="./img/5_t568b.jpg" width=2000px>
  <em>Laman http://portal.ichimarumaru.tech dan konfigurasi T568B</em>
  <p> <br> <br>

### 6. Cari username dan password ketika melakukan login ke FTP Server

Soal ini meminta kita untuk mencari username dan password ketika melakukan login ke FTP Server, caranya menggunakan display filter `Ftp-data` kemudian klik kanan ke datanya cara **Follow -> TCP Stream**
    
  <p align="center">
  <img src="./img/gambar%206.1.jpg" width=2000px>
  <p>
    
  <p align="center">
  <img src="./img/gambar%206.2.jpg" width=2000px>
  <p>

Terdapat cara yang lebih efisien yaitu menggunakan `ftp.request.command == USER or ftp.request.command == PASS`
    
  <p align="center">
  <img src="./img/gambar%206.3.JPG" width=2000px>
  <p>

Keduanya memiliki hasil yang sama, dengan menunjukkan bahwa
Username : secretuser
Password : aku.pengen.pw.aja


### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
  
Dari soal diatas terdapat kata kunci yaitu Real.pdf, lalu gunakan display filter `frame contains "Real.pdf"` 

<p align="center">
  <img src="./img/gambar%207.1.JPG" width=2000px>
 <p>

Kemudian klik kanan cari **Follow -> TCP Stream**
<p align="center">
  <img src="./img/gambar%207.2.JPG" width=2000px>
  <p>
Kemudian ubah file ASCII menjadi RAW
<p align="center">
  <img src="./img/gambar%207.3.JPG" width=2000px>
 <p>
<p align="center">
  <img src="./img/gambar%207.4.JPG" width=2000px>
 <p>

Lalu Save as di driver PC / Laptop masing-masing
<p align="center">
  <img src="./img/gambar%207.5.JPG" width=2000px>
 <p>
Ekstrak atau langsung buka saja, lalu aka nada file Bernama Real.pdf dan ketika di buka akan terdapat gambar dan tulisan “YOU FOUND ME”
<p align="center">
  <img src="./img/gambar%207.6.JPG" width=2000px>
 <p>


### 8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!

Kemudian soal direvisi menjadi "Cari paket yang menunjukan penggunggahan file menuju FTP tersebut!
Untuk yang **pengambilan** file menggunakan `ftp contains “RETR”`  dengan display filter, namun hasilnya tidak ada hasil paket yang menunjukkan pengambilan file
<p align="center">
  <img src="./img/gambar%208.1.JPG" width=2000px>
 <p>

Sedangkan untuk yang **pengunggahan** file menggunakan ftp contains “STOR”  dengan display filter, dan hasilnya terdapat paket yang menunjukkan pengunggahan file

<p align="center">
  <img src="./img/gambar%208.2.JPG" width=2000px>
 <p>


### 9. Dari paket-paket yang menuju FTP terdapat indikasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
   
Soal ini meminta untuk mencari file bernama *“secret.zip”* dan menampilkan isi dari file tersebut serta membukanya.
Pertama menggunakan `ftp-data.command contains "secret.zip"` dengan Display Filter
<p align="center">
  <img src="./img/gambar%209.1.JPG" width=2000px>
 <p>

Kemudian klik kanan cari **Follow -> TCP Stream**

<p align="center">
  <img src="./img/gambar%209.2.JPG" width=2000px>
 <p>

Kemudian ubah file ASCII menjadi RAW
<p align="center">
  <img src="./img/gambar%209.3.JPG" width=2000px>
 <p>

Lalu Save as di driver PC / Laptop masing-masing dengan nama fiile “secret.zip”
<p align="center">
  <img src="./img/gambar%209.4.JPG" width=2000px>
<p>
  
Ekstrak atau langsung buka saja, lalu akan terdapat file Bernama `wanted.pdf` dan ketika di buka akan menyuruh memasukkan password, password dapat dicari di nomer 10 dan ditemukan bahwa passwordnya **d1b1langbukanapaapajugagapercaya**
Dan ketika dimasukkan berisi seperti berikut :

<p align="center">
  <img src="./img/gambar%209.5.JPG" width=2000px>
 <p>
  
<p align="center">
  <img src="./img/gambar%209.6.JPG" width=2000px>
 <p>


### 10. "history.txt" dan password pembuka secret.zip
    
Soal no 10 meminta untuk mencari password pembuka **secret.zip** yang ada di dalam **history.txt**. Untuk itu kita mencari isi dari **history.txt** pada file **8-10.pcap** dengan menggunakan filter `ftp-data.command contains history.txt`. Setelah itu klik kanan pada paket yang tertera, pilih follow TCP Stream. Berikut hasil tangkapan layarnya.
    
  <br>
  <p align="center">
  <img src="./img/10_history.jpg" width=2000px>
  <em>Isi paket history.txt melalui follow TCP Stream</em>
  <p> <br> <br>
    
Di dalamnya terdapat suatu baris berisi
        `key="$(tail -1 bukanapaapa.txt)"`
sehingga diasumsikan, password sebenarnya terdapat pada file **bukanapaapa.txt**
    
Langkah berikutnya yaitu mencari paket yang mengandung **bukanapaapa.txt** dengan menggunakan filter `ftp-data.command contains bukanapaapa.txt`. Lakukan hal yang sama seperti pada **history.txt** yakni klik kanan pada paket yang tertera, pilih follow TCP Stream. Berikut hasil tangkapan layarnya.
    
  <br>
  <p align="center">
  <img src="./img/10_bukanapaapa.jpg" width=2000px>
  <em>Isi paket bukanapaapa.txt melalui follow TCP Stream</em>
  <p> <br> <br> 
    
Didapatkan pesan di dalam **bukanapaapa.txt** berupa :
        ```d1b1langbukanapaapajugagapercaya```
dimana pesan tersebut diasumsikan sebagai password dari file **Wanted.pdf** di dalam **secret.zip**. Dan ternyata benar saja, file **Wanted.pdf** dapat terbuka dengan menggunakan pesan di dalam **bukanapaapa.txt**. Berikut isi file **Wanted.pdf**.
    
  <br>
  <p align="center">
  <img src="./img/10_Wanted.jpg" width=2000px>
  <em>Isi file Wanted.pdf setelah memasukkan password 'd1b1langbukanapaapajugagapercaya'</em>
  <p> <br> <br> 

### 11. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
untuk hanya mengambil paket yang berasal dari port 80, digunakan capture filter **src port 80**. Port 80 digunakan untuk protokol HTTP sehingga harus mengakses website yang menggunakan protokol HTTP agar paket muncul pada wireshark.<br><br>
    ![Capturing from Wi-Fi (src port 80) 9_20_2021 7_49_13 PM](https://user-images.githubusercontent.com/81372291/134593571-e7dbcf22-72a5-4ca7-9646-19bdb7fd57d6.png)


### 12. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
untuk hanya mengambil paket yang mengandung port 21 digunakan capture filter **port 21**. Port 21 digunakan untuk FTP sehingga harus mengakses server FTP agar terdapat paket pada wireshark. Untuk mengakses FTP, bisa dibuka cmd dan memasukkan **ftp localhost**. akan muncul paket pada wireshark.<br><br>
    ![Capturing from Adapter for loopback traffic capture (port 21) 9_20_2021 9_01_20 PM](https://user-images.githubusercontent.com/81372291/134593845-0cc9cab1-c3c2-4262-88cb-300bc6449eb8.png)


### 13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
Untuk hanya menampilkan paket yang menuju port 443 dapat menggunakan capture filter **dst port 443** untuk menangkap paket, lalu digunakan display filter **tcp.port==443 or udp.port==443** agar wireshark hanya menampilkan paket yang menuju port 443.<br><br>
    ![_Wi-Fi (dst port 443) 9_20_2021 8_37_11 PM](https://user-images.githubusercontent.com/81372291/134594182-4ffd71a7-2088-4af5-80e8-7fb3cde3acad.png)


### 14. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!
Untuk hanya mengambil paket yang tujuannya ke kemenag.go.id, digunakan capture filter **dst host kemenag.go.id**, lalu membuka kemenag.go.id pada browser agar paket muncul pada wireshark.<br><br>
    ![Capturing from Wi-Fi (dst host kemenag go id) 9_20_2021 8_26_25 PM](https://user-images.githubusercontent.com/81372291/134594426-425fac50-8d19-4252-a2cd-b434a13be07f.png)


### 15. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
Untuk hanya mengambil paket berasal dari ip sendiri maka harus mencari tahu IP  terlebih dahulu, bisa dilakukan dengan membuka cmd dan memasukkan **ipconfig**. Akan terlihat IP sendiri pada bagian IPv4. untuk hanya mengambil paket yang berasal dari IP sendiri, digunakan capture filter **src host ip**. Untuk IP saya sendiri adalah 192.168.1.3 , sehingga capture filternya adalah **src host 192.168.1.3**.<br><br>
    ![_Wi-Fi (src host 192 168 1 3) 9_24_2021 6_05_43 AM](https://user-images.githubusercontent.com/81372291/134595251-ba39a4a2-dc98-42b5-baf9-b01f9e2a63c7.png)

    
### Kendala yang dialami
    
<li> Pada soal nomor 4 terdapat permintaan dari asdos penguji untuk menggunakan filter yang lebih spesifik
<li> Terdapat username seijaku yang ternyata tidak dapat dipakai login di situs manapun
<li> Dalam pengerjaan nomer 8 agak bingung karena datanya tida ada
<li> Dalam pengerjaan nomer 9 bingung di perbedaan ftp-data contains "secret.zip" dan ftp-data.command contains "secret.zip" karena hasil ketika di save as bentuk raw berbeda
