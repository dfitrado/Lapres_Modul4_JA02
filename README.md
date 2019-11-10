# Lapres_Modul4_JA02
Laporan Praktikum Soal Shift Jarkom oleh grup A02

## Soal Shift Modul 4 - Subnetting & Routing
1. Melakukan perhitungan subnetting VLSM dan CIDR.
2. Mengimplementasikannya ke Cisco Packet Tracer(CPT) dan UML.
3. Ilustrasinya adalah sebagai berikut ini:
<img src="pictures/soal shift modul 4.png" width="800">

## Jawab:
### VLSM
1. Pertama, kita membuat topologi di Cisco Packet Tracer, sesuai soal.

2. Kedua, tambahkan port NM-2FE2W pada semua router terlebih dahulu. khusus untuk router ARCEUS tambahkan port NM-4E.

3. Sambungkan kabel antara sesama router atau dengan switch.

4. Lalu, kita mengelompokkan router dan switch yang ada. Sesama router tidak diperbolehkan untuk berada pada satu kelompok, namu untuk switch diperbolehkan satu kelompok dengan router. Pengelompokkan seperti ilustrasi berikut ini:
<img src="pictures/pembagian vlsm.png" width="600">

5. Setelah dikelompokkan, kita dapat menghitung berapa subnet yang ada per kelompok itu, lalu berapa netmask yang ada di kelompok itu. Kita dapat menghitung dengan menggambar sebuah diagram terlebih dahulu, seperti:
<img src="pictures/perhitungan vlsm.jpg" width="600">

6. Atur IP untuk masing-masing interface yang ada di setiap device sesuai dengan pembagian subnet pada VLSM. Interface dapat diatur pada menu Config -> Interface > “nama interface” (contoh: FastEthernet0/0). Kemudian, isi alamat IP dan subnet mask dari subnet interface tersebut. Berikut contoh untuk mengatur IP pada subnet A1. <br />
Atur IP pada interface CHARIZARD yang mengarah ke client PIPLUP dengan 192.168.30.1.
<img src="pictures/charizard cpt.png" width="600">

7. Kemudian, atur IP pada salah satu client, yaitu PIPLUP yang mengarah ke CHARIZARD. 
<img src="pictures/piplup cpt.png" width="600">

8. Ulangi langkah di atas untuk setiap router, dan juga client lain yang ada.

9. Melakukan routing di setiap router yang ada. Routing dapat dilakukan pada menu Config > Routing > Static pada device Router. Lalu, isilah static routes seperti gambar dibawah pada PIKACHU dan tekan tombol 'Add':
<img src="pictures/pikachu cpt.png" width="600">

Note: Pada static routing juga dibutuhkan default routing agar router dapat mengirimkan paket sesuai dengan tujuan. Default routing dibutuhkan untuk router yang berada di bawah router utama, contoh: VENUSAUR
<img src="pictures/venusaur cpt.png" width="600">

10. Agar semua subnet dapat saling terhubung, tambahkan static routing berikut:
- PIKACHU
```
192.168.31.108/30 via 192.168.31.106
192.168.31.80/29 via 192.168.31.106
192.168.31.0/26 via 192.168.31.106
192.168.0.0/21 via 192.168.31.106
192.168.31.88/30 via 192.168.31.106
192.168.28.0/23 via 192.168.31.106
192.168.20.0/22 via 192.168.31.106 
192.168.31.64/28 via 192.168.31.106
192.168.24.0/23 via 192.168.31.106
192.168.31.92/30 via 192.168.31.102
192.168.30.0/24 via 192.168.31.102
192.168.31.96/30 via 192.168.31.102
192.168.26.0/23 via 192.168.31.102
192.168.16.0/22 via 192.168.31.102
192.168.8.0/21 via 192.168.31.102
10.151.73.68/30 via 192.168.31.102
```

- VENUSAUR
```
192.168.30.0/24 via 192.168.31.94
192.168.26.0/23 via 192.168.31.98
192.168.16.0/22 via 192.168.31.98
192.168.8.0/21 via 192.168.31.98
10.151.73.68/30 via 192.168.31.98
0.0.0.0/0 via 192.168.31.101
```
- CHARIZARD
```
0.0.0.0/0 via 192.168.31.93
```
- ARCEUS
```
0.0.0.0/0 via 192.168.31.97
```
- BLASTOISE
```
192.168.31.80/29 via 192.168.31.110
192.168.31.0/26 via 192.168.31.110
192.168.28.0/23 via 192.168.31.90
192.168.20.0/22 via 192.168.31.90
192.168.31.64/28 via 192.168.31.90
192.168.24.0/23 via 192.168.31.90
0.0.0.0/0 via 192.168.31.105
```
- GIRATINA
```
0.0.0.0/0 via 192.168.31.109
```
- LUGIA
```
0.0.0.0/0 via 192.168.31.89
192.168.24.0/23 via 192.168.20.3
192.168.31.64/28 via 192.168.20.3
```
- DIALGA
```
0.0.0.0/0 via 192.168.20.1
```

Sekian dan terima kasih.
