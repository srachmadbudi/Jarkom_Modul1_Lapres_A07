# Praktikum Modul 1 Jaringan Komputer 2020
Oleh Kelompok A07
* _Clement Prolifel Priyatama (0511184000013)_
* _Ryan Danu Saputra (05111840000144)_

----------------------------------------------------------------
## Soal
* [Nomor 1](#nomor-1)
  * [Nomor 1.a.](#nomor-1a)
  * [Nomor 1.b.](#nomor-1b)
  * [Nomor 1.c.](#nomor-1c)
* [Nomor 2](#nomor-2)
  * [Nomor 2.a. dan 2.b.](#nomor-2a-dan-2b)
  * [Nomor 2.c.](#nomor-2c)
  * [Nomor 2.d.](#nomor-2d)
* [Nomor 3](#nomor-3)
	* [Nomor 3.a.](#nomor-3a)
	* [Nomor 3.b.](#nomor-3b)
	* [Nomor 3.c.](#nomor-3c)
----------------------------------------------------------------

### Nomor 1
 _**Soal:**_\
Sebutkan webserver yang digunakan pada "testing.mekanis.me"!

_**Langkah:**_\
1. Filter `http.host contains "testing.mekanis.me"`
2. Melakukan follow TCP Stream. Didapatkan hasil webserver yaitu Nginx/1.14.0 (Ubuntu)

### Nomor 2
 _**Soal:**_\
Simpan gambar "Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg"!

_**Langkah:**_\
1. Klik `File` - `Export Objects` - `HHTP`
2. Pada `Text Filter`, masukkan nama file `Tim_Kunjungan_Kerja_BAKN_DPR_RI_ke_Sukabumi141436.jpg`. Lalu klik `Save`
3. Hasilnya adalah sebagai berikut:

### Nomor 3
 _**Soal:**_\
Cari username dan password ketika login di "ppid.dpr.go.id"!

_**Langkah:**_\
1. Filter `http.request.method == POST`
2. Pada HTML Form URL Encoded, ditemukan kalau
    Username: 10pemuda
    Password: guncangdunia

### Nomor 4
 _**Soal:**_\
Temukan paket dari web-web yang menggunakan basic authentication method!

_**Langkah:**_\
1. Untuk mencari IP Address dari `testing.mekanis.me`, maka melakukan ping
2. Kemudian untuk mengetahui komunikasi dari `testing.mekanis.me` saja, maka filter komunikasi dari IP 157.245.50.224, dengan cara `ip.addr == 157.245.50.224`
3. Untuk mengetahui paket _basic authentication method_ saja, maka digunakan filter `http.authbasic`

### Nomor 5
 _**Soal:**_\
Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!

_**Langkah:**_\
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
Ikuti perintah di aku.pengen.pw! Username dan password bisa didapatkan dari file .pcapng!

_**Langkah:**_\
1. Filter `ftp-data.command contains zipkey.txt`
2. Lalu, follow TCP Stream, dan ditemukan string berupa `hey997400323051` yang adalah password dari Answer.zip
3. Kemudian, untuk mencari file Yes.pdf, maka dilakukan filter `ftp-data contains Yes.pdf`
4. Setelah paket ditemukan, follow TCP Stream, dan Show and save data as RAW, dan disimpan dengan nama file `Answer.zip`
5. Ekstrak file tersebut dengan menggunakan password `hey997400323051`. Berikut ini adalah isi dari Yes.pdf

