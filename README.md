# Jarkom-Modul-1-IT20-2024

**Kelompok IT20**
| Nama | NRP |
|-----------------------|--------------|
| Clara Valentina | 5027221016 |
| Muhammad Arsy Athallah| 5027221048 |

### Creds

---

Pada soal tersebut, diminta untuk menemukan kredensialn dari server ftp yang dibuat oleh attacker :

a. Apa Username FTP yang digunakan oleh attacker?

b. Apa Password FTP yang digunakan oleh attacker?

Untuk menemukan informasi tersebut, langkah yang dilakukan adalah membuka file evidence.pcap dengan menggunakan wireshark, lalu menggunakan filter `ftp.response.code==230` untuk menemukan informasi login successful.
![Wireshark](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/creds-filter.png)

Kemudian klik kanan, pilih follow untuk melihat informasi detail, termasuk username dan password yang digunakan oleh attacker.
![Wireshark](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/creds-uspass.png)

Lalu memasukkan informasi yang ditemukan pada netcat, untuk mendapatkan flag yang diminta.
![Wireshark](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/creds-flag.png)

### Malwleowleo

---

Pada soal tersebut, diminta untuk menemukan file malware yang dikirim oleh attacker melalui ftp :

a. Apa nama malware yang dikirim oleh attacker ke korban?

Untuk menemukan informasi tersebut, langkah yang dilakukan adalah membuka file evidence.pcap dengan menggunakan wireshark, lalu menggunakan filter `ftp.response.code==230` untuk menemukan informasi login successful.

![Wireshark](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/malweo-filter.png)

Kemudian klik kanan, pilih follow untuk melihat informasi detail, termasuk nama file malware yang dikirim oleh attacker, dengan mencari kata kunci 'STOR' yang merupakan kata kunci untuk upload file ke FTP server.
![Wireshark](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/malweo-mal.png)

Lalu memasukkan informasi yang ditemukan pada netcat, untuk mendapatkan flag yang diminta.
![Wireshark](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/malweo-flag.png)

### ATM or ATP or FTP?

---

Pada soal ini kita disuruh untuk mencari login yang succesful menggunakan filter ftp:

a. Apa password yang berhasil didapatkan oleh hacker setelah melakukan bruteforce login ftp?

Untuk menyelesaikan soal tersebut, langkah pertama adalah memasukkan filter ftp, kemudian klik kanan dengan menggunakan opsi apply settings. Setelah itu tampilan akan menampilkan list dari semua ftp yang ada.

![image](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/assets/128389289/940839b8-3b07-43c9-8408-856ef5a4506d)

Setelah itu cari yang status nya login succesful dan klik kanan lalu follow:

![image](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/assets/128389289/53c74494-22da-4218-a066-7b4080c7c81b)

Itu adalah tampilan setelah di follow dan bisa kita lihat, kita mndapatkan password yang berhasil login

masuk ke bagian netcat, masukkan password yang sudah didapatkan yaitu m4y_th3_Kn!fe_ch1p_&_sh4tter

![atp,atm,ftp](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/assets/128389289/6d74ca5b-addb-4326-8f82-67d24cf2e208)

### Trace Him

---

Pada soal ini mengacu pada soal "ATM or ATP or FTP?" setelah mendapatkan password yang berhasil login, kita langsung saja lihat apa IP Address nya

![image](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/assets/128389289/162f3a30-1900-45f6-845f-536a3c52acad)

Pada gambar diatas bisa dilihat bahwa source dari login successful yaitu 10.30.3.4

![trace him](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/assets/128389289/55c1a4e6-3bba-4266-8419-9fedd1ad629e)

Ditemukanlah Flag nya










## Revisi

### Fuzz

---

Pada soal ini kita diminta untuk mendapatkan username dan password attacker. Pada file capture gunakan filter http.request.method == "POST" dan follow melalui HTTP

![image](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/assets/128389289/3d9ded2c-b2d2-45cf-96d8-8574e7bdb91a)

bisa dilihat bahwa password dan username ditemukan dengan memasukkan "302 found" di kolom search

Selanjutnya masuk ke netcat untuk mencari flagnya

![WhatsApp Image 2024-04-04 at 00 37 40_93741c90](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/assets/128389289/2f494993-cfbe-468e-98df-a8772ed84998)

Flag didapatkan

### Secret

---

Pada soal tersebut, diminta untuk menemukan pesan yang dikirim oleh attacker pada file selain malware. Untuk menemukan file yang dikirim oleh attacker, maka perlu untuk membuka file evidance.pcap terlebih dahulu. Kemudian klik file di bagian kiri atas, lalu pilih export object kemudian pilih ftp-data.

![Secret](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/secret-extract.png)

Kemudian akan ditampilkan 2 file yang telah dikirim oleh attacker, yaitu file malware dan file lain yaitu mirza.jpg. Karena yang diminta adalah pesan selain malwere, maka perlu membuka file mirza.jpg terlebih dahulu dengan menyimpannya.

![Secret](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/secret-save.png)

Kemudian, file mirza.jpg dapat dibuka dan ditemukan pesan yang dikirim oleh attacker, seperti berikut :

![Secret](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/secret-pesen.png)

Lalu memasukkan informasi yang ditemukan pada netcat, untuk mendapatkan flag yang diminta.

![Secret](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/secret-flag.png)


### Evidence

---

Pada soal tersebut, berisikan pertanyaan-pertanyaan berikut :
1. Apa domain milik korban?
2. Apa web server yang digunakan oleh korban?
3. Apa endpoint yang digunakan untuk login sebagai user biasa?
4. Apa email dan password yang berhasil digunakan untuk login sebagai user biasa?

Untuk menjawab pertanyaan-pertanyaan tersebut, maka langkah penyelesaian yang dilakukan adalah menggunakan filter `http` kemudian memilih paket dengan info post.

![Evidence](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/evidance-filter.png)

Lalu klik kanan, pilih follow dengan menggunakan HTTP Stream, sehingga diperoleh hasil sebagai berikut :

![Evidence](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/evidance-tcpstream.png)

Lalu memasukkan informasi yang ditemukan pada netcat, untuk mendapatkan flag yang diminta.

![Evidence](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/SS/evidance-flag.png)



### whoami

---

Case ini berhubungan dengan soal creds dan malwleowleo





