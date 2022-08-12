# Bank-Marketing

![](https://github.com/baressiym/Bank-Marketing/blob/main/telemarketing.jpg)

---
## Business Problem Understanding


### Context :
Sebuah Bank mengajak para nasabah untuk menabung deposito di Bank tersebut dengan cara melakukan *campaign* lewat panggilan telepon (*telemarketing*). Untuk itu, Bank ingin mencari tahu bagaimana respon para nasabah saat menerima panggilan tersebut, apakah para nasabah akan menerima atau menolak ajakan menabung deposito.

Target :
- 0 : Memutuskan untuk tidak menabung deposito. 
- 1 : Memutuskan untuk menabung deposito.


### Problem Statement :
Terdapat 2 kemungkinan dalam melaksanakan strategi*telemarketing*, yaitu pelanggan akan menerima dan memutuskan untuk menabung **ATAU** menolak untuk menabung. Apabila *telemarketing* yang dijalankan tidak efektif, tentu hal ini akan menyebabkan *marketing expenses* meningkat dan Bank akan mengalami kerugian.


### Goals :
Tujuan dari dilakukannya prediksi ini adalah agar Bank mengetahui bagaimana keefektifan strategi marketing mereka dan memetakan mana saja pelanggan yang kemungkinan besar tertarik dan memutuskan untuk menabung deposito, sehingga tidak perlu mengeluarkan biaya yang terlalu besar untuk biaya pemasaran (*marketing expenses*).


### Analytic Approach :
Dari permasalahan-permasalahan ini, yang perlu dilakukan adalah untuk menganalisis dan menemukan pola pelanggan yang memutuskan untuk menabung deposito dan yang tidak.


### Metric Evaluation :
- True Positive (TP) : Pelanggan memutuskan untuk menabung deposito.

- False Positive (FP) : Kita memprediksi pelanggan setuju menabung, padahal aktualnya tidak setuju.

- False Negative (FN) : Kita memprediksi pelanggan tidak setuju menabung, padahal aktualnya setuju.

- True Negative (TN) : Pelanggan memutuskan untuk tidak menabung deposito.


Dari penjabaran di atas, risiko akan lebih tinggi ketika terjadi **False Negative**. Hal ini dikarenakan pelanggan yang SETUJU untuk menabung deposito, dianggap TIDAK SETUJU untuk menabung sehingga pelanggan yang berpotensi untuk menabung hilang dan menyebabkan kerugian bagi Bank. Sehingga False Negative perlu untuk diminimalisir. Measure yang akan digunakan adalah **Recall Positif** atau **Precision Negative**.



## Data Understanding


### About the Data :
Dataset yang digunakan didapat dari Lembaga Bank di Portugal dari tahun 2008 sampai tahun 2013. Perlu diketahui bahwa pada tahun 2008, terjadi *Great Recession* (Krisis Finansial 2007-2012) yang menimpa seluruh dunia, tidak terkecuali Portugal.





---

### Let's get in touch!

|  [LinkedIn](https://www.linkedin.com/in/baressi/)  |  [GitHub](https://github.com/baressiym)  | [Tableau](https://public.tableau.com/app/profile/baressi.yehezkiel) |
