# Jarkom-Modul-1-E12-2021
Anggota :
- Ahmad Luthfi Hanif	  - 05111940000179
- Rahadian Adjie Mahesa	- 05111940000221
- Afifan Syafaqo Yahya	- 05111940000234
 
## Soal 1 (Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!)
1. Mengisi pada *Display Filter* **http.host == "ichimarumaru.tech"** untuk menampilkan host dengan domain ichimarumaru.tech
![soal1](https://user-images.githubusercontent.com/55140514/134492368-c9acdedd-b9d5-4173-9985-47c23252fa72.png)

2. Untuk mencari webserver nya bisa kita gunakan follow TCP Stream dengan melakukan klik kanan pada salah satu hasil yang telah terfilter (disini dipilih yang GET / HTTP/1.1 karena ini adalah webnya) dan mencari kata-kata *Server*
![soal1Server](https://user-images.githubusercontent.com/55140514/134492375-f04a2029-289a-4ae0-847f-ffc8943e6053.png)

### Jawaban
Filter Expression : **http.host == "ichimarumaru.tech**

Webserver : **nginx/1.18.0 (Ubuntu)**

## Soal 2 (Temukan paket dari web-web yang menggunakan basic authentication method!)
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

## Soal 4 (Temukan paket mysql yang mengandung perintah query select!)
Pada soal ini untuk menemukan perintah Query Select bisa seperti berikut
1. Pada *Display Filter* bisa kita isi *Filter Expression* **mysql contains select** tetapi karena ada kemungkinan penulisan select dengan huruf kapital semua ada dan wireshark case sensitive maka kita menggunakan *Logical Operator* **Or** agar bisa mendapatkan semuanya. Maka filter akan menjadi **mysql contains select or mysql contains SELECT**. Hasil seperti berikut.
![soal4](https://user-images.githubusercontent.com/55140514/134679265-356b552a-5984-4964-b9a1-a3381d66e6dc.png)

### Jawaban
Filter Expression : **mysql contains select or mysql contains SELECT**

## Soal 5 (Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!)
Pengerjaan pada soal ini sama seperti pada soal nomor 4
1. Pada *Display Filter* bisa kita isi *Filter Expression* **mysql contains insert or mysql contains INSERT**
![image](https://user-images.githubusercontent.com/55140514/134700609-ed63596f-766d-4061-b5b9-3a03dead716e.png)
2. Untuk mendapatkan *username* dan *password* bisa kita lihat dari **MySQL Protocol** dan pada **Statement** diliat *values* nya
![image](https://user-images.githubusercontent.com/55140514/134706330-e4f50f43-a4fa-4289-8588-9fe28ec271c2.png)
3. Setelah itu kita ambil *username* dan *password* nya dan dimasukkan ke dalam web tersebut. Berikut adalah web-nya
![soal5portal](https://user-images.githubusercontent.com/55140514/134680387-f49aade5-b050-41e2-b005-05791641d708.png)

### Jawaban
Filter Expression : **mysql contains insert or mysql contains INSERT**

## Soal 6 (Cari username dan password ketika melakukan login ke FTP Server!)  
1. mencari **username** dari FTP server yang sudah disediakan, kami menggunakan filter dengan format `ftp contains USER` untuk mencari usernama tersebut dan didapat bahwasannya  "*secretuser*" merupakan salah satu nama username yang dicari seperti gambar sebagai berikut  
![image](https://user-images.githubusercontent.com/75328763/134771671-6e6918cc-0b35-45df-b983-a722f586f5ad.png)
2. mencari **password** dari FTP server yang sama, kami menggunakan filter dengan format `ftp contains PASS` dan diapat sebagai gambar di bawah, bisa dilihat "aku.pengen.pw.aja" sebagaimana gambar berikut  
![image](https://user-images.githubusercontent.com/75328763/134771689-fe2cc025-9903-4b1d-9871-125af178bc81.png)  
  
### Jawaban  
Username : *secretuser*  
Password : *aku.pengen.pw.aja*  

## Soal 7 (Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf"))  
1. untuk mencari 500 zip yang tersedia dimana salah satu dari itu ada yang mempunyai isi file pdf bernama "Real.pdf" kami menggunakan filter `ftp-data contains "Real.pdf"`  
![image](https://user-images.githubusercontent.com/75328763/134772943-326bc3ef-eaa1-4d99-a950-42c812b6feac.png)  

2. lalu kami membuka isi dari "Real.pdf" sebagaimana berikut.  
![image](https://user-images.githubusercontent.com/75328763/134772995-b9bec706-6256-4837-8201-37c368adf7a8.png)  

## Soal 8 (Cari paket yang menunjukan pengambilan file dari FTP tersebut!)  
1. untuk mengetahui adanya pengambilan data (downloaded) dari FTP server yang telah disediakan, kami menggunakan filter `ftp contains RETR` unntuk menge-check apakah ada data yang berhasil didownload. dan yang kami temukan hasilnya adalah **tidak ada** sebagaimana gakmbar berikut  
![image](https://user-images.githubusercontent.com/75328763/134772272-feeb993b-655a-46dc-a31d-ceb2dac434cb.png)  
### Jawaban  
**KOSONG*  

## Soal 9 (Dari paket-paket yang menuju FTP terdapat inidkasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!)  
1. kami menggunakan filter `ftp-data.command contains "secret.zip"` untuk mencari file bernama "secret.zip" dan bisa dilihat ada banyak paket yang tersimpan, dipilih satu secara acak dan melakukan *follow TCP Stream* dan didapat adanya data dalam FTP tersebut sebagiamana gambar berikut  
![image](https://user-images.githubusercontent.com/75328763/134772468-cfc1d646-8b24-4a04-8f82-1317ad7de8dd.png)  
2. setelah itu kami download file tersebut dan direname dengan format *.zip* lalu dibuka dan muncul isi seperti dibawah ini.  
![image](https://user-images.githubusercontent.com/75328763/134772510-d840ebad-8672-4d9a-96c8-cd5d1c56159b.png)

## Soal 10 (Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!)  
1. untuk membuka isi menggunkan password pad zip yang telah ditemukan pada soal seblumnya, kami mencari clue dengan membuka file "history.txt" menggunakan filter `ftp-data.command contains "history.txt"` sebagai berikut. ditunjukan bahwasannya clue password berada pada file "bukanapaapa.txt"  
![image](https://user-images.githubusercontent.com/75328763/134772603-75a6adf9-51e8-4c57-a6b7-9e2844153e25.png)  

2. lalu kami menggunakan filter lagi seperti `ftp-data.command contains "bukanapaapa.txt"` dan dilihat menggunakan *follow TCP Stream* kami menemukan sebuah string yang kami duga itu merupakan password dari "secrett.zip". passwordnya adalah `d1b1langbukanapaapajugagapercaya`. gambar sebagai berikut.  
![image](https://user-images.githubusercontent.com/75328763/134772717-6745e329-bb57-4b1a-8414-926947d083e5.png)  

3. kami lalu membuka file "secret.zip" menggunakan password tersbut dan terbukalah file yang bernama "Wanted.pdf" yang berisi sebagai berikut.  
![image](https://user-images.githubusercontent.com/75328763/134772800-c4fba6ce-6640-482f-8fc0-5ed672a84240.png)


## Soal 11 (Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!)
Berikut langkah-langkah pengerjaan soal ini
1. Input **src port 80** sebagai filter pada kolom capture filter
![soal11](https://raw.githubusercontent.com/ALuthfiH/Image/image/Screenshot%20(233).png)
2. Kemudian kami membuka situs **http://monta.if.its.ac.id/** agar paket yang berasal dari port 80 dapat diambil oleh wireshark
![image](https://raw.githubusercontent.com/ALuthfiH/Image/image/Screenshot%20(234).png)
3. Berikut paket yang diambil dari port 80
![image](https://raw.githubusercontent.com/ALuthfiH/Image/image/Screenshot%20(235).png)

## 12 (Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!)
Untuk pengerjaan nomor ini diperlukan server FTP terlebih dahulu. Kita menggunakan FileZilla dalam pembuatan server tersebut
1. Membuat server FileZilla. Start Filezilla Server
![image](https://user-images.githubusercontent.com/55140514/134707335-b4ce7080-1a55-448f-80b0-045aaffbd612.png)
2. Pada FileZilla Serve GUI pencet Connect to FTP Filezilla FTP Server
![image](https://user-images.githubusercontent.com/55140514/134707538-3070ef76-747a-4581-af51-e9d11b933bff.png)
3. Lalu, pada Filezilla Client kita masukkan Host serta username nya. Setelah itu dipencet quickconnect
![image](https://user-images.githubusercontent.com/55140514/134707676-de8f2ab9-f9e4-47f0-b675-abc4cb3b0cca.png)
4. Setelah server FTP terbuat, kita bisa melakukan *Capture* di Wireshark. Pada wireshark kita isi di *Capture Display* nya dengan **port 21** agar menampilkan semua yang menggunakan port 21 / FTP. Seperti berikut
![soal12](https://user-images.githubusercontent.com/55140514/134503887-0ad07ed6-c8f2-4165-b586-e03ffabbc02b.png)

### Jawaban
Filter Expression : Pada *Capture Display* **port 21** 

## Soal 13 (Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!)
Berikut langkah-langkah pengerjaan soal
1. Masukkan filter **dst port 443** pada kolom capture filter untuk menampilkan paket yang menuju port 443
![filter](https://raw.githubusercontent.com/ALuthfiH/Image/main/Screenshot%20(243).png)
3. Berikut paket-paket yang menuju port 443 
![paket](https://raw.githubusercontent.com/ALuthfiH/Image/main/Screenshot%20(244).png)

## Soal 14 (Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!)
Berikut langkah-langkah pengerjaan soal nomor 14
1. Masukkan filter **dst host kemenag.go.id** pada kolom capture filter untuk menngambil paket
![filter](https://raw.githubusercontent.com/ALuthfiH/Image/main/Screenshot%20(239).png)
3. Buka situs **https://www.kemenag.go.id/** agar paket dapat diambil oleh wireshark
![situs](https://raw.githubusercontent.com/ALuthfiH/Image/main/Screenshot%20(240).png)
5. Berikut paket yang tujuannya ke **https://www.kemenag.go.id/**
![paket](https://raw.githubusercontent.com/ALuthfiH/Image/main/Screenshot%20(241).png)


## Soal 15 (Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!)
Berikut langkah-langkah pengerjaan soal nomor 15
1. Pertama-tama kita harus melakukan pengecekkan terhadap IP Address kita sendiri. Kita dapat mengecek IP Address kita melalui setting ataupun Command Prompt. Berikut IP Address saya setelah dicek pada Command Prompt
![ip](https://raw.githubusercontent.com/ALuthfiH/Image/image/Capture2.JPG)
2. Setelah itu, input **ip src 192.168.100.8** sebagai filter pada kolom capture filter
![filter](https://raw.githubusercontent.com/ALuthfiH/Image/image/Screenshot%20(236).png)
3. Berikut paket yang berhasil ditangkap dari IP Address sendiri
![hasil](https://raw.githubusercontent.com/ALuthfiH/Image/image/Screenshot%20(237).png)

