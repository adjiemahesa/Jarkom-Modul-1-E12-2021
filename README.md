# Jarkom-Modul-1-E12-2021
Anggota :
- Ahmad Luthfi Hanif	  - 05111940000179
- Rahadian Adjie Mahesa	- 05111940000221
- Afifan Syafaqo Yahya	- 05111940000234
 
## Soal 1 (Menampilkan Webserver pada ichimarumaru.tech)
1. Mengisi pada *Display Filter* **http.host == "ichimarumaru.tech"** untuk menampilkan host dengan domain ichimarumaru.tech
![soal1](https://user-images.githubusercontent.com/55140514/134492368-c9acdedd-b9d5-4173-9985-47c23252fa72.png)

2. Untuk mencari webserver nya bisa kita gunakan follow TCP Stream dengan melakukan klik kanan pada salah satu hasil yang telah terfilter (disini dipilih yang GET / HTTP/1.1 karena ini adalah webnya) dan mencari kata-kata *Server*
![soal1Server](https://user-images.githubusercontent.com/55140514/134492375-f04a2029-289a-4ae0-847f-ffc8943e6053.png)

### Jawaban
Filter Expression : **http.host == "ichimarumaru.tech**

Webserver : **nginx/1.18.0 (Ubuntu)**

## Soal 2 (Mencari paket-paket dari web-web yang menggunakan Basic Authentication)
1. Untuk mendapatkannya digunakan *Filter Expression* pada *Display Filter* **http.authorization contains Basic** atau bisa juga menggunakan **http.authbasic**
![soal2](https://user-images.githubusercontent.com/55140514/134683594-d68dd7ba-7b98-4027-af8c-c6af64d540ed.png)

### Jawaban
Filter Expression : **http.authorization contains Basic** atau **http.authbasic**

## Soal 3 (Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!)
Pada soal ini diminta untuk mengakses web **basic.ichimarumaru.tech** dimana web tersebut perlu memasukkan *username* serta *password* yang bisa kita cari menggunakan wireshark
1. Untuk mendapatkannya *username* serta *password* kita bisa langsung menggunakan fitur **Find Packet** yang ada di edit. Lalu pada find Packet tersebut kita mengganti agar mencari Packet Details nya serta yang dicari adalah String. Lalu, kita isi pada kolom kosongnya **Credentials**.
![image](https://user-images.githubusercontent.com/55140514/134686297-2ed6c695-4459-45c6-9b8e-5aee883f59e9.png)
2. Nanti akan didapatkan seperti berikut
![soal3](https://user-images.githubusercontent.com/55140514/134687110-cf3318ce-ed0d-41f8-b435-7bd9193c26a7.png)
3. Lalu dicek padaa *Hypertext Transfer Protocol* pada authorization nya ada Credentials yang berisi **username:password** 
![image](https://user-images.githubusercontent.com/55140514/134686797-47d37d56-196b-477a-972a-c4e1bb30cf9d.png)
4. Lalu, dimasukkan pada web tersebut *username* serta *password* nya dan akan keluar web berikut
![soal3basic](https://user-images.githubusercontent.com/55140514/134686999-b471216f-2e73-440f-a5ea-a6fc7931fb98.png)

*Notes*
Untuk soal ini bisa juga kita filter terlebih dahulu untuk ke website **basic.ichimarumaru.tech** dengan menggunakan **http.host == "basic.ichimarumaru.tech"** seperti pada soal 1. kita lakukan ini agar hanya mendapatkan dan melihat *Credentials* yang hanya ada di web tersebut. Setelah kita filter baru kita lakukan langkah Find Packet seperti diatas. Hasilnya Seperti Berikut
![image](https://user-images.githubusercontent.com/55140514/134687798-02fd0c41-8f01-4985-a9c5-b75cdeb6a189.png)

### Jawaban
Menggunakan Find Packet (**Edit -> find packet -> Packet Details -> String -> pada kolom kosong kita tulis Credential**)
atau bisa juga menggunakan filter expression **http.host == "basic.ichimarumaru.tech"** terlebih dahulu
## 4
![soal4](https://user-images.githubusercontent.com/55140514/134679265-356b552a-5984-4964-b9a1-a3381d66e6dc.png)


## 5
![soal5](https://user-images.githubusercontent.com/55140514/134503749-80f58677-a09a-4585-a040-239f26eccc5b.png)
![soal5portal](https://user-images.githubusercontent.com/55140514/134680387-f49aade5-b050-41e2-b005-05791641d708.png)

## 6

## 7
## 8
## 9
## 10
## 11
![soal11](https://user-images.githubusercontent.com/55140514/134503854-a805092d-5706-47f8-b343-73a898334b3b.png)

## 12
![soal12](https://user-images.githubusercontent.com/55140514/134503887-0ad07ed6-c8f2-4165-b586-e03ffabbc02b.png)

## 13

## 14
![soal14](https://user-images.githubusercontent.com/55140514/134504096-2bc2fea0-e91b-41fc-89c2-48b1f2cc4784.png)

## 15
