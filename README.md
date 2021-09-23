# Soal Shift Praktikum 1 Jarkom 2021

<li> Jonathan Timothy Siregar - 05111940000120
<li> Muhammad Fikri Sandi Pratama - 05111940000195
<li> Mohammad Thoriq Huda - 05111940000207
<br><br><br>

### 1. Webserver yang digunakan pada "ichimarumaru.tech"


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

### 6


### 7


### 8


### 9


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
