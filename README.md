# Praktikum Modul 1 Jaringan Komputer 2020
Oleh Kelompok A07
* _Clement Prolifel Priyatama (0511184000013)_
* _Ryan Danu Saputra (05111840000144)_

----------------------------------------------------------------
## Soal
* [Nomor 1](#nomor-1)
* [Nomor 2](#nomor-2)
* [Nomor 3](#nomor-3)
* [Nomor 4](#nomor-4)
* [Nomor 5](#nomor-5)
* [Nomor 6](#nomor-6)
* [Nomor 7](#nomor-7)
* [Nomor 8](#nomor-8)
* [Nomor 9](#nomor-9)
* [Nomor 10](#nomor-10)
* [Nomor 11](#nomor-11)
* [Nomor 12](#nomor-12)
* [Nomor 13](#nomor-13)
* [Nomor 14](#nomor-14)
* [Nomor 15](#nomor-15)
--------------------------------------------------------------

### Nomor 1
 _**Soal:**_\
Sebutkan webserver yang digunakan pada "testing.mekanis.me"!

_**Langkah:**_
1. Filter `http.host contains "testing.mekanis.me"`
![1_1](https://raw.githubusercontent.com/prolifel/Jarkom_Modul1_Lapres_A07/main/img/1_1.jpg)
2. Melakukan follow TCP Stream. Didapatkan hasil webserver yaitu Nginx/1.14.0 (Ubuntu)

![1_2](https://raw.githubusercontent.com/prolifel/Jarkom_Modul1_Lapres_A07/main/img/1_2.jpg)

### Nomor 2
 _**Soal:**_\
Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!

_**Langkah:**_
1. Klik `File` - `Export Objects` - `HHTP`
2. Pada `Text Filter`, masukkan nama file `Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg`. Lalu klik `Save`

![2_1](https://raw.githubusercontent.com/prolifel/Jarkom_Modul1_Lapres_A07/main/img/2_1.jpg)

3. Hasilnya adalah sebagai berikut:

![2_2](https://raw.githubusercontent.com/prolifel/Jarkom_Modul1_Lapres_A07/main/img/2_2.jpg)

### Nomor 3
 _**Soal:**_\
Cari username dan password ketika login di "ppid.dpr.go.id"!

_**Langkah:**_
1. Filter `http.request.method == POST`

![3_1](https://raw.githubusercontent.com/prolifel/Jarkom_Modul1_Lapres_A07/main/img/3_1.jpg)

2. Pada HTML Form URL Encoded, ditemukan kalau
    Username: 10pemuda
    Password: guncangdunia
    
![3_2](https://raw.githubusercontent.com/prolifel/Jarkom_Modul1_Lapres_A07/main/img/3_2.jpg)

### Nomor 4
 _**Soal:**_\
Temukan paket dari web-web yang menggunakan basic authentication method!

_**Langkah:**_
1. Untuk mencari IP Address dari `testing.mekanis.me`, maka melakukan ping

![4_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/4_1.jpg?raw=true)

2. Kemudian untuk mengetahui komunikasi dari `testing.mekanis.me` saja, maka filter komunikasi dari IP 157.245.50.224, dengan cara `ip.addr == 157.245.50.224`. Untuk mengetahui paket _basic authentication method_ saja, maka digunakan filter `http.authbasic`. Sehingga, filter yang digunakan yaitu `ip.addr == 157.245.50.224 && http.authbasic`

![4_2](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/4_2.jpg?raw=true)

### Nomor 5
 _**Soal:**_\
Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!

_**Langkah:**_
1. Filter `frame contains "aku.pengen.pw"`

![5_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/5_1.jpg?raw=true)

2. Pada paket GET /networking_meme.png HTTP/1.1, ditemukan Authorization dengan Credentials: kakakgamtenk:hartatahtabermuda. Maka username dan password adalah kakakgamtenk:hartatahtabermuda

![5_2](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/5_2.jpg?raw=true)

3. Setelah login pada aku.pengen.pw, jawaban soalnya adalah 
1 : Putih Orange 

2 : Orange  

3 : Putih Hijau 

4 : Biru 

5 : Putih Biru 

6 : Hijau 

7 : Putih Coklat 

8 : Coklat

![5_3](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/5_3.jpg?raw=true)

### Nomor 6
 _**Soal:**_\
Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).

_**Langkah:**_
1. Filter `ftp-data.command contains zipkey.txt`

![6_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/6_1.jpg?raw=true)

2. Lalu, follow TCP Stream, dan ditemukan string berupa `hey997400323051` yang adalah password dari Answer.zip

![6_2](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/6_2.jpg?raw=true)

3. Kemudian, untuk mencari file Answer.pdf, maka dilakukan filter `ftp-data.command contains Answer.zip`

![6_3](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/6_3.jpg?raw=true)

4. Setelah paket ditemukan, follow TCP Stream, dan Show and save data as RAW, dan disimpan dengan nama file `Answer.zip`

![6_4](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/6_4.jpg?raw=true)

5. Ekstrak file tersebut dengan menggunakan password `hey997400323051`. Berikut ini adalah isi dari `Open This.pdf`

![6_5](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/6_5.jpg?raw=true)

### Nomor 7
 _**Soal:**_\
Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.
Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"

_**Langkah:**_
1. Filter `ftp-data contains Yes.pdf`

![7_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/7_1.jpg?raw=true)

2. Kemudian, follow TCP Stream, dan Show and save data as RAW, dan disimpan dengan nama file `473.zip`

![7_2](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/7_2.jpg?raw=true)

3. Ekstrak file tersebut, dan ditemukan Yes.pdf. Berikut ini adalah isi dari Yes.pdf

![7_3](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/7_3.jpg?raw=true)

### Nomor 8
 _**Soal:**_\
Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!

_**Langkah:**_
1. Untuk mencari IP destination dari koneksi FTP dengan Microsoft FTP Service, maka menggunakan filter `ftp contains Microsoft`. Kemudian, klik kanan pada salah satu paket kolom Source, dan klik Apply as Filter - Selected

![8_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/8_1.jpg?raw=true)

2. Untuk mencari file yang didownload, maka filter ditambah menjadi `ftp.request.command == RETR && ip.dst == 198.246.117.106`. Maka ditemukan file yang didownload adalah `Readne`

![8_2](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/8_2.jpg?raw=true)

### Nomor 9
 _**Soal:**_\
Cari username dan password ketika login FTP pada localhost!

_**Langkah:**_
1. Untuk mencari username dari FTP, maka menggunakan filter `ftp.request.command eq USER`. Didapatkan username nya adalah `dhana`

![9_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/9_1.jpg?raw=true)

2. Untuk mencari password dari FTP, maka menggunakan filter `ftp.request.command eq PASS`. Didapatkan username nya adalah `dhana123`

![9_2](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/9_2.jpg?raw=true)

### Nomor 10
_**Soal:**_\
Cari file .pdf di wireshark lalu download dan buka file tersebut!
clue: "25 50 44 46"

_**Langkah:**_
1. http.request.method == "GET"
![10_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/10_1.jpg)

2. Follow Tcp stream file pdfnya 
[10_2](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/10_2.jpg)

3. Show and save data as raw 
[10_3](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/10_3.jpg)

4. Save as diberi nama dengan format  ( .pdf	)
Hasilnya 
[10_4](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/10_4.jpg)

### Nomor 11
_**Soal:**_\
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!

Tcp.port == 21
[11_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/11_1.jpg)


### Nomor 12
_**Soal:**_\
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!

Tcp.srcport == 80
[12_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/12_1.jpg)


### Nomor 13
_**Soal:**_\
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!

tcp.dstport == 43
[13_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/13_1.jpg)

### Nomor 14
_**Soal:**_\
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

_**Langkah:**_
1. Liat ip di cmd lewat perintah ipconfig
[14_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/14_1.jpg)

2. Lalu buka di wireshark dengan menggunakan perintah ip.src == 192.168.0.3 (yaitu ip kita)
[14_2](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/14_2.jpg)



### Nomor 15
_**Soal:**_\
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke monta.if.its.ac.id!


_**Langkah:**_
1. Ping monta.if.its.ac.id agar mengetahui ip nya di cmd
[15_1](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/15_1.jpg)

2. Lalu gunakan ip.dst == 103.94.190.11 
[15_2](https://github.com/prolifel/Jarkom_Modul1_Lapres_A07/blob/main/img/15_2.jpg)


