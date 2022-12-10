# **Jarkom-Modul-5-C11-2022**

*Repository* ini berisi laporan resmi dari praktikum modul 5 dari mata kuliah Jaringan Komputer tahun 2022.

</br>

## **Data Diri**
| Nama | Kelas-Kelompok | NRP |
| ------------- | ------------- | ------------- |
| Nur Muhammad Ainul Yaqin | C-11 | 5025201011 |

</br>

## **Laporan Pengerjaan**

Laporan ini berisi penjelasan dari soal-soal yang dikerjakan pada modul 5 hingga masa revisi selesai.

</br>

### **Persiapan**

Sebagai persiapan, terdapat beberapa poin yang harus dilakukan yang tertuang dalam soal sebagai berikut.

**1. Tugas pertama kalian yaitu membuat topologi jaringan sesuai dengan rancangan yang diberikan Loid dibawah ini.**

Pada poin ini, telah dibuat topologi pada GNS3 sebagai berikut.

![Gambar Topologi yang Dibuat](./img/topologi.png)

Nantinya, terdapat beberapa node yang memiliki peran khusus, yaitu sebagai berikut.

- Eden adalah DNS Server
- WISE adalah DHCP Server
- Garden dan SSS adalah Web Server
- Jumlah Host pada Forger adalah 62 host
- Jumlah Host pada Desmond adalah 700 host
- Jumlah Host pada Blackbell adalah 255 host
- Jumlah Host pada Briar adalah 200 host

</br>

**2. Untuk menjaga perdamaian dunia, Loid ingin meminta kalian untuk membuat topologi tersebut menggunakan teknik CIDR atau VLSM setelah melakukan subnetting.**

Pada poin ini, dilakukan perhitungan subnetting dengan menggunakan metode VLSM. Metode ini diawali dengan melakukan pengelompokan pada topologi yang telah dibuat sebagai berikut.

![Gambar Pengelompokan](./img/area.png)

Selanjutnya, dilakukan analisis sehingga didapatkan hasil sebagai berikut.

| Subnet | Jumlah IP Host | Netmask |
| ------------- | ------------- | ------------- |
| A1 | 3 | /29
| A2 | 701 | /22
| A3 | 63 | /25
| A4 | 2 | /30
| A5 | 2 | /30
| A6 | 256 | /23
| A7 | 201 | /24
| A8 | 3 | /29


Berdasarkan total IP host dan netmask yang dibutuhkan, root subnet yang dibentuk memiliki NID 10.15.0.0 dengan netmask /21 dan jumlah IP Host sebanyak 1231. Kemudian, alokasi IP Address secara keseluruhan dapat dibuat menjadi seperti berikut.

| Subnet (Alias) | Jumlah IP Host | Alokasi | NID | Available Hosts | Broadcast Address | Netmask |

| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |

| A2 | 701 | 1022 | 10.15.0.0 | 10.15.0.1 - 10.15.3.254 | 10.15.3.255 | 255.255.255.128
| A6 | 256 | 510 | 10.15.4.0 | 10.15.4.1 - 10.15.5.254 | 10.15.5.255 | 255.255.254.0
| A7 | 201 | 254 | 10.15.6.0 | 10.15.6.1 - 10.15.6.254 | 10.15.6.255 | 255.255.255.0
| A3 | 63 | 126 | 10.15.7.0 | 10.15.7.1 - 10.15.7.126 | 10.15.7.127 | 255.255.252.0
| A1 | 3 | 6 | 10.15.7.128 | 10.15.7.129 - 10.15.7.134 | 10.15.7.135 | 255.255.255.248
| A8 | 3 | 6 | 10.15.7.136 | 10.15.7.137 - 10.15.7.142 | 10.15.7.143 | 255.255.255.248
| A4 | 2 | 2 | 10.15.7.144 | 10.15.7.145 - 10.15.7.146 | 10.15.7.147 | 255.255.255.252
| A5 | 2 | 2 | 10.15.7.148 | 10.15.7.149 - 10.15.7.150 | 10.15.7.151 | 255.255.255.252


Tidak lupa, dibuat `IP Address Tree` untuk mempermudah visualisasi dari subnetting yang telah dibuat sebagai berikut.

![Gambar Tree](./img/tree.png)




















## **Kendala yang Dihadapi**
Terdapat beberapa kendala saat pengerjaan praktikum, antara lain sebagai berikut.

1. Tantangan dalam manajemen pekerjaan dan waktu, karena dikerjakan sendiri tanpa adanya pembagian task.
2. Stuck pada nomor terakhir, yaitu pada logging. Logging sendiri masih belum terselesaikan dengan baik meskipun telah mengikuti dan mengelaborasi beberapa referensi terpercaya.