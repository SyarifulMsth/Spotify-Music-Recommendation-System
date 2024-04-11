
# Music Recommendation System [Spotify Dataset]
<p align='center'><img src="https://github.com/SyarifulMsth/Spotify-Music-Recommendation-System-/blob/main/images/music.avif?raw=true"  width="1000"></p>
 
## 🧭 Domain Proyek

### Latar Belakang

Industri musik saat ini mengalami perkembangan yang sangat pesat. Saat ini musik sangat mudah didengarkan di mana saja dan kapan saja oleh siapa pun. Hal tersebut tidak terlepas dari pesatnya perkembangan teknologi dan internet saat ini, yang memberikan kontribusi dalam perkembangan musik di dunia. Berdasarkan sebuah survei yang dilakukan oleh Asosiasi Penyelenggaran Jasa Internet Indonesia, menyatakan bahwa 33,5% dari seluruh pengguna internet di Indonesia mendengarkan music secara *online*. <sup>[1]</sup>

Berdasarkan kecenderungan dan kondisi tersebut, banyak perusahaan yang bergerak di bidang *content digital* membuat dan mengembangkan berbagai aplikasi pemutar musik *online*.<sup>[1]</sup> Saat ini terdapat berbagai layanan untuk mendengarkan musik secara *online*, di antaranya yaitu iTunes, Spotify, Google Play Music, Pandora, Grooveshark, dan masih banyak lagi yang lainnya.<sup>[2]</sup> Dari berbagai layanan atau *platform* tersebut, mereka memiliki kesamaan yaitu mempunyai fitur untuk mencari lagu berdasarkan *tagging* atau label yang disimpan sebagai informasi pada setiap musik atau lagu. Namun, tidak jarang hasil dari pencarian tersebut menghasilkan hasil yang tidak sesuai dengan apa yang ingin didengar oleh pengguna. Misalnya ketika seseorang melakukan pencarian dengan memasukkan kata "Pop", maka akan muncul hasil musik-musik dengan label Pop. Akan tetapi, seringkali tidak adanya filter atau penyaringan mengenai lagu Pop yang benar-benar ingin didengar oleh pengguna. Akibatnya hasil pencarian menjadi terlalu general dan tidak tepat sasaran.<sup>[2]</sup>

Berdasarkan urian latar belakang permasalahan yang telah dijabarkan, pada proyek ini dibuat untuk membangun sebuah sistem rekomendasi musik yang dapat digunakan untuk meningkatkan kualitas hasil pencarian musik pada sebuah aplikasi. Sistem rekomendasi musik yang akan dibangun yaitu dengan menggunakan algoritma *content based filtering*. Sehingga diharapkan dengan adanya proyek ini dapat memberikan rekomendasi musik yang lebih baik kepada pengguna berdasarkan genre musik yang ingin pengguna dengar.

## 📌 Business Understanding

### Problem Statement
Berdasarkan latar belakang permasalahan yang telah diuraikan sebelumnya, maka pada proyek ini dapat diambil rumusan masalah (*problem statements*) sebagai berikut : 
1. Bagaimana memberikan rekomendasi musik atau lagu berdasarkan genre dengan menggunakan algoritma *machine learning*?
2. Bagaimana mengembangkan model *machine learning* yang dapat digunakan untuk memberikan rekomendasi musik kepada pengguna berdasarkan genre musik yang ingin didengar?
3. Bagaimana performa atau evaluasi dari model *machine learning* yang telah dikembangkan untuk memberikan rekomendasi musik kepada pengguna?  

### Goals
Berdasarkan rumusan masalah (*problems statement*) yang telah dirumuskan sebelumnya, maka berikut adalah tujuan (*goals*) dari proyek *machine learning* ini :
1. Mengetahui penerapan algoritma *machine learning* dalam memberikan rekomendasi musik berdasarkan genre.
2. Mengetahui rangkaian proses pengembangan model *machine learning* dari awal hingga selesai dalam memberikan rekomendasi musik berdasarkan genre.
3. Mengetahui performa atau evaluasi dari model *machine learning* yang telah dikembangkan untuk memberikan rekomendasi musik berdasarkan genre.

### Solution Statements
Berdasarkan *problem statements* dan *goals* yang telah disebutkan sebelumnya, maka berikut adalah *solution statements* pada proyek *machine learning* ini : 
1.   Melakukan proses pengembangan model *machine learning* dari awal hingga selesai, meliputi *data wrangling*, *Exploratory Data  Analysis* (EDA), *modelling*, dan *evaluation*.
2. Pengembangan model *machine learning* (*modelling*) menggunakan algoritma yang sesuai dengan permasalahan, yaitu algoritma *content based filtering* dengan menggunakan dataset yang telah ditentukan. 
3. Melakukan *evaluation model* untuk mengetahui performa model dengan menggunakan metriks evaluasi yang sudah ditentukan. *Evaluation* model dilakukan untuk mengetahui performa dari model yang telah dikembangkan dalam memberikan rekomendasi musik berdasarkan genre. Sehingga dapat diketahui model *machine learning* yang terbaik untuk digunakan dalam memberikan rekomendasi musik berdasarkan genre.
 

## 📚 Data Understanding 
Pada proyek ini dataset yang digunakan adalah [Dataset Top Hits Spotify from 2000-2019](https://www.kaggle.com/datasets/paradisejoy/top-hits-spotify-from-20002019). Dataset tersebut terdiri dari 2000 *data records* dengan 18 *features*. 
### Variabel Dataset
Berikut adalah detail dari *features* dataset yang digunakan dalam pengembangan model *machine learning* proyek ini : 

Tabel 1. Dataset Top Hits Spotify from 2000-2019
| Attribute | Description | Data Type |
|---|---|---|
| artist | Nama artis yang membawakan lagu | Text |
| song | Judul lagu | Text |
| duration_ms | Durasi lagu dalam milidetik | Integer |
| explicit | Menunjukkan apakah lagu mengandung lirik atau konten eksplisit | Boolean |
| year | Tahun rilis lagu | Integer |
| popularity | Popularitas lagu | Integer |
| danceability | Seberapa cocok lagu untuk menari berdasarkan kombinasi elemen musik | Decimal (0.0 - 1.0) |
| energy | Intensitas dan aktivitas lagu | Decimal (0.0 - 1.0) |
| key | Kunci lagu | Integer (merujuk pada skala musikal) |
| loudness | Kekuatan suara lagu dalam desibel (dB) | Decimal |
| mode | Menunjukkan skala lagu, mayor (nilai 1) atau minor (nilai 0) | Integer |
| speechiness | Probabilitas adanya kata-kata yang diucapkan dalam lagu | Decimal (0.0 - 1.0) |
| acousticness | Tingkat kepercayaan apakah lagu akustik | Decimal (0.0 - 1.0) |
| instrumentalness | Probabilitas bahwa lagu tidak mengandung vokal | Decimal (0.0 - 1.0) |
| liveness | Probabilitas bahwa lagu direkam secara live | Decimal (0.0 - 1.0) |
| valence | Positivitas yang disampaikan oleh sebuah lagu | Decimal (0.0 - 1.0) |
| tempo | Tempo keseluruhan estimasi dari sebuah lagu dalam ketukan per menit (BPM) | Integer |
| genre | Genre dari lagu | Text |

**Notes:**
* The data type "Decimal" indicates a numeric value that ranges between 0.0 and 1.0.
* The data type "Integer" indicates a numeric value without a decimal point.
  
## 📚 Data Preparation
*Data preparation* adalah proses mempersiapkan data mentah menjadi format yang sesuai untuk analisis atau pemrosesan lebih lanjut. Berikut adalah beberapa teknik atau metode yang digunakan dalam persiapan data pada proyek ini:

1. **Handling missing value** 
	- *Missing value* merupakan salah satu masalah yang paling sering dijumpai dalam proyek analisis data di industri. Masalah ini muncul karena adanya nilai yang hilang dari sebuah data dan biasanya direpresentasikan sebagai nilai NaN dalam library pandas. Hal ini biasanya terjadi karena adanya *human error*, masalah privasi, proses *merging/join*, dll. 
	- Tujuan dari langkah ini adalah untuk memastikan keakuratan dan keandalan data yang digunakan untuk analisis atau pemodelan. *Missing value* dapat menyebabkan bias dan kesalahan dalam analisis data, sehingga penting untuk mengidentifikasi dan mengatasi nilai yang hilang ini agar hasil analisis menjadi lebih akurat dan dapat diandalkan.
		
2. **Handling duplicated data**
	- *Duplicated data* adalah masalah lain yang umum dijumpai di industri. Ia terjadi ketika terdapat sebuah observasi (semua nilai dalam satu unit baris) yang memiliki nilai yang sama persis pada setiap kolomnya. 
	-  Tujuan dari langkah ini adalah untuk memastikan integritas data. *Duplicated data* dapat mempengaruhi analisis data dan membuat hasil yang tidak akurat. Oleh karena itu, dengan mengidentifikasi dan menghapus data yang terduplikat, dapat memastikan bahwa data yang digunakan untuk analisis atau pemodelan adalah data yang valid dan representatif.
	-  Salah satu teknik yang dapat digunakan dalam mengatasi *duplicated data* adalah dengan menghapus data yang terduplikat (*dropping*).		

3. **Feature Engineering**
<br> *Feature Engineering* merupakan sebuah proses untuk mengembangkan dan memilih suatu fitur atau atribut (features) yang akan digunakan untuk melakukan analisis data atau dalam melakukan pembuatan sebuah model machine learning. 
	
	Pada proyek ini tahapan *feature engineering* dilakukan pada *features* data genre. Pada *features* genre terdapat beberapa data yang memiliki lebih dari satu genre. Sehingga perlu dilakukan penanganan, yaitu dengan memilih genre pada kategori pertama. Hal ini dilakukan agar memudahkan pengembangan model dan menghasilkan model dengan performa yang baik. 

## 🎯 Modeling
Pada proyek ini algoritma machine learning yang digunakan di antaranya yaitu *Content Based Filtering*.

### Content Based Filtering 
*Content Based Filtering* merupakan metode yang digunakan dalam sistem rekomendasi dan analisis data yang berfokus pada karakteristik atau konten dari item-item yang ingin direkomendasikan atau dianalisis. Pendekatan tersebut menggunakan atribut-atribut atau *features* item untuk menentukan kesamaan antara item yang ada dan preferensi pengguna.

<p align='center'><img src="https://github.com/SyarifulMsth/Spotify-Music-Recommendation-System-/blob/main/images/content_based_filltering.png?raw=true"  width="500"></p>
<p align='center'>Gambar 4. Algoritma Content Based Filtering</p> 

**Kelebihan** : 
- Dapat memberikan rekomendasi yang lebih personalisasi karena mempertimbangkan preferensi pengguna yang sudah diketahui.
- Tidak memerlukan data eksternal seperti data pengguna lainnnya, sehingga mudah untuk diimplementasikan ketika data pengguna terbatas

**Kekurangan** : 
- Tidak mampu memberikan rekomendasi untuk item yang sangat berbeda dengan preferensi pengguna sebelumnya. 
- Rentan terhadap *overfitting* apabila model terlalu bergantung pada *attribut* atau *features* yang terlalu spesifik.

### Implementasi  
Berikut adalah tahapan *modelling* menggunakan algoritma *Content Based Filtering* pada proyek ini, di antaranya : 
- Vektorisasi dengan *TF-IDF* 
	Pada tahap ini data yang telah dibersihkan dan siap digunakan akan dikonversi menjadi bentuk vekor dengan menggunakan *function TfidfVectorizer()* dari *library* scikit-learn. Pada tahapan ini, telah berhasil dilakukan identifikasi representasi *feature* dengan menggunakan *function [TfidfVectorizer()](https://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfVectorizer.html)*

- Melakukan perhitungan derajat kesamaan (*cosine similarity*) 
	Pada tahapan ini dilakukan perhitungan derajat kesamaan (*cosine similarity*) dengan menggunakan *function* *[cosine_similarity](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.pairwise.cosine_similarity.html)* pada *dataframe* tfidf_matrix yang telah diperoleh pada tahapan sebelumnya. Pada tahapan ini dilakukan perhitungan kesamaan (*similarity*) antar musik atau lagu berdasarkan genre. 

- Membuat rekomendasi musik atau lagu 
	Pada tahapan ini dilakukan pembuatan fungsi *lagu_recommendations*, yang menggunakan *argpartition*. Pada tahapan ini diambil sejumlah nilai *k* tertinggi dari *similarity* data (dalam proyek ini : **cosine_sim_df**). Kemudian, diambil data dari bobot (tingkat kesamaan) tertinggi ke terendah. Data tersebut dimasukkan ke dalam variabel *closest*. Selanjutnya, menghapus lagu yang dicari agar tidak muncul dalam daftar rekomendasi. 

### Hasil
Tahapan pengembangan model *machine learning* rekomendasi musik atau lagu telah berhasil dibuat. Tahap selanjutnya yaitu melihat bagaimana hasil dari rekomendasi musik atau lagu yang dibuat. 

Dalam kasus ini, akan dicari lagu yang mirip dengan lagu dari Taylor Swift dengan judul **Love Story** yang bergenre **Pop**.

Tabel.2 Informasi musik atau lagu untuk uji coba
| artist       | song       | year | popularity | genre |
|--------------|------------|------|------------|-------|
| Taylor Swift | Love Story | 2008 | 74         | pop   |

Tabel 3. Hasil rekomendasi musik atau lagu berdasarkan genre 
|    | song              | genre |
|----|-------------------|-------|
| 0  | TiK ToK           | pop   |
| 1  | All The Right Moves | pop |
| 2  | Paparazzi         | pop   |
| 3  | Release Me        | pop   |
| 4  | If U Seek Amy     | pop   |

Pada tabel 2 di atas diperoleh 5 rekomendasi musik atau lagu kepada pengguna berdasarkan genre, dalam kasus ini genre yang direkomendasikan yaitu *Pop* sesuai dengan lagu Taylor Swift yang berjudul Love Story. 


## 📈 Evaluation
Proyek *machine learning* ini dikembangkan dengan menggunakan algoritma *Content Based Filtering*, sehingga metrik evaluasi model yang akan digunakan pada proyek ini menggunakan *Precision*. *Precision* dapat didefinisikan sebagai berikut : 

$\text{Precision} = \frac{r}{i}$

- r = Total rekomendasi yang relevan
- i = Jumlah rekomendasi yang diberikan
  
Berdasarkan hasil pengujian yang telah dilakukan pada **subbab Hasil**, telah diperoleh hasil 5 rekomendasi musik atau lagu berdasarkan genre. Apabila dilakukan perhitungan untuk mengetahui bagaimana performa atau evaluasi dari model menggunakan formula di atas maka diperoleh nilai **Precision = 5/5 = 100%**

## Conclusion
Pengembangan model *machine learning* rekomendasi musik atau lagu dengan menggunakan algoritma *Content Based Filtering* membutuhkan beberapa tahapan yang bersifat iteratif, mulai dari *business understanding*, *data understanding*, dan seterusnya hingga tahapan *modelling* dan *evaluation*. Selain itu, berdasarkan dengan konteks data, *problem statements*, dan solusi yang diimplementasikan, metrik evaluasi yang digunakan pada proyek *machine learning* ini menggunakan *precision*. *Precision* digunakan untuk mengukur berapa banyak model menghasilkan prediksi/rekomendasi yang benar. Berdasarkan tahapan evaluasi diperoleh model *machine learning* rekomendasi musik atau lagu berdasarkan genre dengan hasil yang memuaskan, dengan nilai **precision 100%**. Model machine learning dengan menggunakan algoritma *content based filtering* yang telah dikembangkan pada proyek ini dinilai mampu menjawab *problem statements* dan mencapai *goals* dari proyek yang sudah ditentukan sebelumnya. Sehingga diharapkan dengan adanya model machine learning ini dapat membantu memberikan rekomendasi musik berdasarkan genre pada aplikasi layanan musik *online*.

## References

[1] M. V. Anggoro and M. Izzatillah, “Sistem Rekomendasi Musik dengan Metode Collaborative Filtering Berbasis Android,” _STRING (Satuan Tulisan Ris. dan Inov. Teknol._, vol. 7, no. 1, p. 1, 2022, doi: 10.30998/string.v7i1.10300.

[2] T. Saptariani, “Sistem Rekomendasi Musik Menggunakan Latent Semantic Analysis,” _Pros. Semin. Ilm. Nas. Komput. dan Sist. Intelijen (KOMMIT 2014)_, vol. 8, no. Kommit, pp. 416–424, 2014.

## 🔗 Links
[![portfolio](https://img.shields.io/badge/my_portfolio-000?style=for-the-badge&logo=ko-fi&logoColor=white)](https://syarifulmsth.github.io) [![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/syariful-musthofa/) [![twitter](https://img.shields.io/badge/twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/)

## Feedback
*If you have any feedback, please reach out at* syarifulm007@gmail.com
