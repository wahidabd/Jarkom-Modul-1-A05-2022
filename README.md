# Kelompok A05
* NRP - Nama
* NRP - Nama
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