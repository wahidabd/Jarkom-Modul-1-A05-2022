# Kelompok A05
* 5025201039 - Abd. Wahid
* 5025201197 - Abidjanna Zulfa Hamdika
* 5025201020 - Muhammad Ferdian Iqbal
<br><br>

### 1. Sebutkan web server yang digunakan pada "monta.if.its.ac.id"!

<br>

> Langkah pengerjaan 
- Tulis command **http.request and http.host eq "monta.if.its.ac.id"**
- Akan muncul informasi sebagai berikut

![Gambar 1.1](./images/1.1.jpg)

- Pada informasi tersebut, dipilih salah satu. Lalu, klik kanan, follow --> tcp stream. Akan muncul informasi web server yang digunakan

![Gambar 1.2](./images/1.2.jpg)

> Web server yang digunakan adalah **NginX**

<hr>
<br>

### 2. Ishaq sedang bingung mencari topik ta untuk semester ini , lalu ia datang ke website monta dan menemukan detail topik pada website “monta.if.its.ac.id” , judul TA apa yang dibuka oleh ishaq?

<br>

> Langkah pengerjaan 
- Tulis command **http.request and http.host eq "monta.if.its.ac.id"**
- Akan muncul informasi sebagai berikut

![Gambar 1.1](./images/1.1.jpg)

- Terdapat request GET ke /index.php/topik/detailTopik/194

![Gambar 2.1](./images/2.1.jpg)

- Export object HTML untuk mendapatkan file

![Gambar 2.2](./images/2.2.jpg)

- Save file dengan nama 194 karena menurut request, file tersebut berisi detail topik

![Gambar 2.3](./images/2.3.jpg)

- Tambahkan ekstensi .html di belakang nama file dan buka filenya

![Gambar 2.4](./images/2.4.jpg)

> Judul TA = **Evaluasi unjuk kerja User Space Filesystem (FUSE)**
<hr> <br>


### 3. Filter sehingga wireshark hanya menampilkan paket yang menuju port 80!


<br>

> Langkah pengerjaan
- Ketikkan command **tcp.dstport == 80**

![Gambar 3.1](./images/3.1.jpg)

<hr> <br>

### 4. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 21


<br>

> Langkah pengerjaan
- Ketikkan command **tcp.srcport == 21**

![Gambar 4.1](./images/4.1.jpg)

<hr> <br>

### 5. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 443!

<br>

> Langkah pengerjaan
- Ketikkan command **tcp.srcport == 443**

![Gambar 5.1](./images/5.1.jpg)

<hr> <br>

### 6. Filter sehingga wireshark hanya menampilkan paket yang menuju ke lipi.go.id !

<br>

> Langkah pengerjaan
- Ping lipi.go.id, dapat IP 203.160.128.158

![Gambar 6.1](./images/6.1.jpg)

- Ketikkan command **ip.dst == 203.160.128.158**

![Gambar 6.2](./images/6.2.jpg)

<hr> <br>

### 7. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!

<br>

> Langkah pengerjaan
- Cek ping devices terlebih dahulu

![Gambar 7.1](./images/7.1.jpg)

- Ketikkan command **ip.src == IP kalian**

![Gambar 7.2](./images/7.2.jpg)

<hr> <br>

### 8. Telusuri aliran paket dalam file .pcap yang diberikan, cari informasi berguna berupa percakapan antara dua mahasiswa terkait tindakan kecurangan pada kegiatan praktikum.

> Langkah pengerjaan
- Merujuk pada soal no 9 yang ada ekstensi des3 dengan ini kami mencari percakapan command frame matches “des3
![Gambar 8.1](./images/8.1.jpg)

- Follow TCP stream untuk melihat percakapan
![Gambar 8.2](./images/8.2.jpg)

- Detail percakapan adalah sebagai berikut
![Gambar 8.3](./images/8.3.jpg)

- Terlihat bahwa percakapan tersebut disimpan di stream 12. Untuk menemukan percakapan lain, perlu mengganti streamnya. 
![Gambar 8.4](./images/8.4.jpg)

- Percakapan kedua akhirnya ditemukan di stream 41
![Gambar 8.5](./images/8.5.jpg)

- Percakapan ketiga ditemukan di stream 90
![Gambar 8.6](./images/8.6.jpg)

- Total percakapan lengkap yang ditemukan ada 3, yaitu di stream 12, 41, dan 90

<hr> <br>

### 9. Terdapat laporan adanya pertukaran file yang dilakukan oleh kedua mahasiswa dalam percakapan yang diperoleh, carilah file yang dimaksud!

> Langkah pengerjaan
- Menurut percakapan di stream 12, pelaku akan mengirim file salt menggunakan port 9002. Maka kita perlu mencari file yang dikirimkan melalui port 9002. Ketikkan filter berikut **tcp.srcport==9002**
![Gambar 9.1](./images/9.1.jpg)

- Berdasarkan percakapan tersebut juga, file yang akan dikirimkan adalah file salt. Berdasarkan hasil yang ditemukan, hanya paket 61 yang berisikan file salt
![Gambar 9.2](./images/9.2.jpg)

- Export dan beri nama sesuai ketentuan serta tambahkan ekstensi des3. Nama file akan menjadi A05.des3. Decode file tersebut menggunakan password di nomor 10 dan akan keluar hasil file flag
![Gambar 9.3](./images/9.3.jpg)

- Detail isi dari file flag
![Gambar 9.4](./images/9.4.jpg)

<hr> <br>

### 10. Temukan password rahasia (flag) dari organisasi bawah tanah yang disebutkan di atas!

> Langkah pengerjaan
- Berdasarkan percakapan di stream 12, clue dari password adalah karakter anime yang kembar lima. Anime yang dimaksud adalah Gotoubun no Hanayome. Dalam anime tersebut, kembar 5 tersebut memiliki nama keluarga "nakano". "nakano" inilah yang menjadi password dari file tersebut. Password dipastikan benar berdasarkan file flag yang didapatkan di nomor 9


