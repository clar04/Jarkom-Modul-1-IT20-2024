# Jarkom-Modul-1-IT20-2024

**Kelompok IT20**
|        Nama           |     NRP      |
|-----------------------|--------------|
| Clara Valentina       | 5027221016   |
| Muhammad Arsy Athallah| 5027221048   |

## Soal "creds"
 Pada soal tersebut, diminta untuk menemukan kredensialn dari server ftp yang dibuat oleh attacker :
 
 a. Apa Username FTP yang digunakan oleh attacker?
 
 b. Apa Password FTP yang digunakan oleh attacker?

 Untuk menemukan informasi tersebut, langkah yang dilakukan adalah membuka file evidence.pcap dengan menggunakan wireshark, lalu menggunakan filter `ftp.response.code==230` untuk menemukan informasi login successful.
 ![Wireshark](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/creds-filter.png)

Kemudian klik kanan, pilih follow untuk melihat informasi detail, termasuk username dan password yang digunakan oleh attacker. 
 ![Wireshark](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/creds-uspass.png)

Lalu memasukkan informasi yang ditemukan pada netcat
![Wireshark](https://github.com/clar04/Jarkom-Modul-1-IT20-2024/blob/main/creds-flag.png)

## Soal "malwleowleo"
Pada soal tersebut, diminta untuk menemukan file malware yang dikirim oleh attacker melalui ftp :

a. Apa nama malware yang dikirim oleh attacker ke korban?


