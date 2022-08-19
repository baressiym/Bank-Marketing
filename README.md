# Bank-Marketing

![](https://github.com/baressiym/Bank-Marketing/blob/main/telemarketing.jpg)



## Business Problem Understanding


### Context :

Di tahun 2008, terjadi *Great Recession* di seluruh dunia. *Great Recession* sendiri adalah sebuah fenomena melemahnya kegiatan ekonomi yang paling signifikan, yang terjadi dalam pada tahun 2007 sampai 2009. Menurut European Central Bank di tahun 2008, margin deposito bank di kawasan Eropa telah menurun tajam sejak akhir 2008. Hal ini memaksa bank bersaing untuk mendapatkan dana simpanan yang lebih stabil. Namun, dengan menurunnya suku bunga deposito, menyebabkan Bank kehilangan nasabahnya untuk menyimpan uang.

Di dalam kasus ini, Bank tersebut mengajak para nasabah untuk deposito di Bank tersebut denagan melakukan *telemarketing*. Untuk itu, dengan kondisi di yang "terjepit", sebuah Bank merekrut seorang Data Scientist untuk mengetahui, siapa saja nasabahnya yang memiliki tendensi untuk deposit dan yang tidak.

Target :
- 0 : Memutuskan untuk tidak menabung deposito. 

- 1 : Memutuskan untuk menabung deposito.


### Problem Statement :

Dalam kasus ini, proses *telemarketing* dilakukan secara *in-house*, di mana segala proses *telemarketing* dilakukan oleh bank, tidak menggunakan tenaga outsourcing. 

Disadur dari glassdoor, rata-rata gaji *telemarketer* (asumsikan dalam US Dollar) sebesar USD30,688 dengan bonus sebesar USD4,633 per tahun. (Diasumsikan bahwa sistem pembayaran yang dilakukan adalah per jam*). Ditambah lagi dengan adanya *Customer Service Manager* yang memiliki rata-rata gaji sebesar USD39,694 dengan bonus sebesar USD6,032 per tahun. Di dalam kasus ini, diasumsikan bahwa terdapat 10 orang *telemarketer* di dalam sebuah tim. 

Disadur dari cloudtask, *potential cost* dari *in-house telemarketing team* ini dapat dijabarkan sebagai berikut:

- Salaries and Benefit : USD353,210
- Customer Service Managet : USD45,726
- Hiring costs : USD20,645
- Office space : USD48,000
- Software and Hardware : USD3,600
- Trainers, phone system, tax, office supply, etc : USD200,000

Total : USD671,181 per year

Dengan asumsi di atas, Bank harus mengeluarkan kurang lebih sebesar USD671,181 per tahun. Tentu angka tersebut cukup besar dan akan sangat merugikan apabila pelanggan yang ditelepon memutuskan untuk tidak deposito. Ditambah lagi dengan adanya *great recession*, Bank tidak ingin kehilangan pelanggannya.


### Goals :

Tujuan utama dari project ini adalah untuk membuat sebuah model Machine Learning, di mana Bank akan mengetahui tendensi pelanggan untuk deposito, apakah setuju untuk deposit atau tidak setuju, sebelum proses *telemarketing* dieksekusi. Dengan permasalahan bahwa Bank tidak ingin *expenses* membengkak dan Bank tidak ingin kehilangan pelanggannya, model yang dibuat juga harus bertujuan untuk mereduksi permasalahan-permasalahan tersebut.

Untuk mencapai tujuan-tujuan tersebut, kita juga perlu menentukan perlakuan-perlakuan setelah model dilakukan. Perlakuan ini dilakukan dengan asumsi terdapat batasan jumlah budget yang dikeluarkan untuk marketing.


### Project Limitation
Dataset yang digunakan pada Project ini didapat dari Purwadhika Digital Technology School. Dataset digunakan hanya untuk project saja, sehingga untuk penjelasan-penjelasan detail dari Bank yang melakukan prediksi tidak ditampilkan. Hasil dari project ini terbatas haya untuk menghasilkan model Machine Learning yang memprediksi apakah pelanggan memutuskan untuk deposito atau tidak.


### Metric Evaluation :
#### True Positive (TP) : 

"Pelanggan memutuskan untuk menabung deposito."

**Impact:** Kita mendapatkan keuntungan karena nasabah yang kita hubungi memang benar memutuskan untuk deposit.

#### False Positive (FP) : 

"Kita memprediksi pelanggan setuju menabung, padahal aktualnya tidak setuju."

**Impact:** Hal ini merugikan karena proses *telemarketing* menjadi sia-sia dan menyebabkan marketing expenses justru meningkat.

#### False Negative (FN) : 

"Kita memprediksi pelanggan tidak setuju menabung, padahal aktualnya setuju."

**Impact:** Hal ini merugikan karena kita baru saja kehilangan pelanggan potensial.

#### True Negative (TN) : 

"Pelanggan memutuskan untuk tidak menabung deposito."

**Impact:** Kita tidak mendapatkan pemasukan dari deposito.

Berdasarkan kosekuensinya, False Positive dan False Positive memiliki risiko yang sama-sama tinggi bagi perusahaan. Maka perlu dibuat model yang dapat meminimalisir expenses tapi tetap menjaga keberadaan customer. Sehingga, measure yang akan digunakan dalam model ini adalah f1 score.


### Why Using Machine Learning???

Tanpa menggunakan Machine Learning, Bank akan menelepon semua nasabah yang terdaftar tanpa mengetahui latar belakang dari tiap-tiap nasabah yang dihubungi. Hal ini kurang efektif karena peluang bahwa jumlah pegeluaran untuk *telemarketing* lebih besar dibandingkan jumlah pemasukan dari nasabah yang melakukan deposito akan sangat besar apabila kita tidak mengetahui terlebih dahulu *feature-feature* apa saja yang mempengaruhi nasabah untuk menentukan pilihan. Sebagai contoh, apabila per jamnya seorang *telemarketer* dibayar USD75 per jam untuk melakukan proses *telemarketing* dengan asumsi *telemarketer* tersebut bekerja selama 8 jam di dalam sehari. Dalam sehari, seorang *telemarketer* tersebut akan mendapatkan sebesar USD600. Apabila selama 8 jam tersebut nasabah yang dihubungi mayoritas menolak dengan ajakan untuk deposit, tentu uang yang dikeluarkan oleh Bank akan sia-sia.

Dengan menggunakan Machine Learning, proses *telemarketing* akan menjadi jauh lebih efektif karena nasabah yang dihubungi hanyalah nasabah yang memiliki potensi tinggi untuk melakukan deposit. Apabila selama 8 jam tersebut nasabah yang dihubungi mayoritas setuju dengan ajakan untuk deposit, tentu uang yang dikeluarkan oleh Bank akan tidak akan sia-sia.


### Attribute Information :
**1. age:**
Usia dari nasabah Bank

**2. job:**
Jenis pekerjaan dari nasabah Bank

**3. balance:**
Jumlah kredit atau deposit dari seseorang nasabah
- (+) : Deposit
- (-) : Kredit

**4. housing:**
Apakah nasabah memiliki pinjaman berupa Kredit Pemilikian Rumah (*housing loan*)? 

**5. loan**
Apakah nasabah memiliki pinjaman pribadi terhadap Bank?

**6. contact**
Cara *telemarketer* menghubungi nasabah.

**7. month**
Bulan terakhir nasabah dihubungi

**8. campaign:**
Jumlah telepon dilakukan selama *campaign*.

**9. pdays**
Jumlah hari yang terlewat setelah nasabah terakhir kali dihubungi dari kampanye sebelumnya.

**10. poutcome**
Hasil dari *campaign* sebelumnya.

**11. deposit:**
Target kita, apakah nasabah setuju untuk deposit atau tidak?



---

### Let's get in touch!

|  [LinkedIn](https://www.linkedin.com/in/baressi/)  |  [GitHub](https://github.com/baressiym)  | [Tableau](https://public.tableau.com/app/profile/baressi.yehezkiel) |
