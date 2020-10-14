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
2. Melakukan follow TCP Stream. Didapatkan hasil webserver yaitu Nginx/1.14.0 (Ubuntu)

### Nomor 2
 _**Soal:**_\
Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!

_**Langkah:**_
1. Klik `File` - `Export Objects` - `HHTP`
2. Pada `Text Filter`, masukkan nama file `Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg`. Lalu klik `Save`
3. Hasilnya adalah sebagai berikut:

### Nomor 3
 _**Soal:**_\
Cari username dan password ketika login di "ppid.dpr.go.id"!

_**Langkah:**_
1. Filter `http.request.method == POST`
2. Pada HTML Form URL Encoded, ditemukan kalau
    Username: 10pemuda
    Password: guncangdunia

### Nomor 4
 _**Soal:**_\
Temukan paket dari web-web yang menggunakan basic authentication method!

_**Langkah:**_
1. Untuk mencari IP Address dari `testing.mekanis.me`, maka melakukan ping
2. Kemudian untuk mengetahui komunikasi dari `testing.mekanis.me` saja, maka filter komunikasi dari IP 157.245.50.224, dengan cara `ip.addr == 157.245.50.224`. Untuk mengetahui paket _basic authentication method_ saja, maka digunakan filter `http.authbasic`. Sehingga, filter yang digunakan yaitu `ip.addr == 157.245.50.224 && http.authbasic`

### Nomor 5
 _**Soal:**_\
Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!

_**Langkah:**_
1. Filter `frame contains "aku.pengen.pw"`
2. Pada paket GET /networking_meme.png HTTP/1.1, ditemukan Authorization dengan Credentials: kakakgamtenk:hartatahtabermuda. Maka username dan password adalah kakakgamtenk:hartatahtabermuda
3. Setelah login pada aku.pengen.pw, jawaban soalnya adalah 
1 : Putih Orange 
2 : Orange  
3 : Putih Hijau 
4 : Biru 
5 : Putih Biru 
6 : Hijau 
7 : Putih Coklat 
8 : Coklat

### Nomor 6
 _**Soal:**_\
Seseorang menyimpan file zip melalui FTP dengan nama "Answer.zip". Simpan dan Buka file "Open This.pdf" di Answer.zip. Untuk mendapatkan password zipnya, temukan dalam file zipkey.txt (passwordnya adalah isi dari file txt tersebut).

_**Langkah:**_
1. Filter `ftp-data.command contains zipkey.txt`
2. Lalu, follow TCP Stream, dan ditemukan string berupa `hey997400323051` yang adalah password dari Answer.zip
3. Kemudian, untuk mencari file Answer.pdf, maka dilakukan filter `ftp-data.command contains Answer.zip`
4. Setelah paket ditemukan, follow TCP Stream, dan Show and save data as RAW, dan disimpan dengan nama file `Answer.zip`
5. Ekstrak file tersebut dengan menggunakan password `hey997400323051`. Berikut ini adalah isi dari `Open This.pdf`

### Nomor 7
 _**Soal:**_\
Ada 500 file zip yang disimpan ke FTP Server dengan nama 1.zip, 2.zip, ..., 500.zip. Salah satunya berisi pdf yang berisi puisi. Simpan dan Buka file pdf tersebut.
Your Super Mega Ultra Rare Hint = nama pdf-nya "Yes.pdf"

_**Langkah:**_
1. Filter `ftp-data contains Yes.pdf`
2. Kemudian, follow TCP Stream, dan Show and save data as RAW, dan disimpan dengan nama file `473.zip`
3. Ekstrak file tersebut, dan ditemukan Yes.pdf. Berikut ini adalah isi dari Yes.pdf

### Nomor 8
 _**Soal:**_\
Cari objek apa saja yang didownload (RETR) dari koneksi FTP dengan Microsoft FTP Service!

_**Langkah:**_
1. Untuk mencari IP destination dari koneksi FTP dengan Microsoft FTP Service, maka menggunakan filter `ftp contains Microsoft`. Kemudian, klik kanan pada salah satu paket kolom Source, dan klik Apply as Filter - Selected
2. Untuk mencari file yang didownload, maka filter ditambah menjadi `ftp.request.command == RETR && ip.dst == 198.246. 117.106`. Maka ditemukan file yang didownload adalah `Readne`

### Nomor 9
 _**Soal:**_\
Cari username dan password ketika login FTP pada localhost!

_**Langkah:**_
1. Untuk mencari username dari FTP, maka menggunakan filter `ftp.request.command eq USER`. Didapatkan username nya adalah `dhana`
2. Untuk mencari password dari FTP, maka menggunakan filter `ftp.request.command eq PASS`. Didapatkan username nya adalah `dhana123`

