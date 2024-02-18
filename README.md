# Reccomendation System: Book Reccomendation
By: Made Rahano Satryani Widhi

## Project Overview

Dengan kemajuan teknologi dan transformasi digital yang terus berkembang, platform daring dan aplikasi telah menjadi sumber utama informasi dan rekomendasi bagi pembaca. Setiap tahun, industri penerbitan menyaksikan ledakan buku baru di berbagai genre, yang pada satu sisi menawarkan pembaca akses ke beragam pilihan, tetapi juga menimbulkan tantangan dalam menemukan buku yang sesuai dengan minat dan preferensi individu. Dalam konteks ini, proyek rekomendasi buku menjadi semakin penting, karena memungkinkan pembaca untuk menemukan buku-buku yang sesuai dengan minat mereka dengan lebih efisien. Dengan menggunakan algoritma rekomendasi yang canggih, proyek ini bertujuan untuk meningkatkan pengalaman membaca pembaca, mengarahkan mereka ke bacaan yang paling relevan dan menarik, sambil juga berpotensi memperluas wawasan literer dan mendukung perkembangan industri penerbitan secara keseluruhan.

## Business Understanding

### Problem Statements

- Tantangan Identifikasi Kesesuaian Buku dengan Preferensi Pengguna:

  Bagaimana sistem rekomendasi dapat mengidentifikasi kesesuaian buku dengan preferensi pengguna secara akurat? Apakah terdapat metode yang efektif untuk menganalisis preferensi pengguna dan memetakannya ke dalam fitur-fitur yang relevan dari buku? Tantangan utama dalam pembangunan sistem rekomendasi adalah menavigasi kompleksitas preferensi pengguna dan beragamnya opsi buku yang tersedia. Oleh karena itu, menjadi penting untuk mengembangkan pendekatan yang dapat mengidentifikasi kesesuaian buku dengan preferensi pengguna secara efisien dan akurat, memungkinkan pengguna untuk menemukan buku yang paling sesuai dengan minat mereka.

- Kompleksitas Analisis Data Pengguna dan Konten Buku:

  Bagaimana sistem dapat mengatasi kompleksitas data pengguna, seperti preferensi dan riwayat bacaan, untuk menghasilkan rekomendasi yang personal? Apakah ada metode yang efektif untuk menganalisis atribut konten buku, seperti judul, genre, dan deskripsi, untuk mengidentifikasi kesamaan antara buku-buku? Proses analisis data pengguna dan konten buku merupakan langkah krusial dalam menghasilkan rekomendasi yang relevan. Namun, kompleksitas atribut dan volume data memunculkan tantangan dalam memahami preferensi pengguna serta mengekstrak informasi yang relevan dari buku-buku yang tersedia.

- Optimasi Kinerja Model Rekomendasi:

  Bagaimana sistem dapat mengoptimalkan kinerja model Content-Based Filtering dan Collaborative Filtering secara bersamaan? Apakah terdapat strategi yang efektif untuk mengintegrasikan kedua pendekatan ini guna meningkatkan kualitas rekomendasi secara keseluruhan? Dalam pengembangan sistem rekomendasi, penting untuk mempertimbangkan bagaimana menggabungkan kekuatan dari kedua pendekatan utama, yaitu Content-Based Filtering dan Collaborative Filtering. Diperlukan pendekatan yang dapat mengoptimalkan kinerja keduanya secara bersamaan, memungkinkan sistem untuk memberikan rekomendasi buku yang lebih akurat dan relevan kepada pengguna.

### Goals

- Pengembangan Sistem Rekomendasi Buku yang Efektif:

  Tujuan utama proyek ini adalah untuk mengembangkan sebuah sistem rekomendasi buku yang efektif dalam memberikan rekomendasi yang relevan dan sesuai dengan minat pengguna. Sistem ini diharapkan dapat membantu pengguna menemukan buku-buku yang sesuai dengan preferensi mereka, meningkatkan pengalaman membaca, dan memperluas wawasan literer.

- Personalisasi Rekomendasi:

  Sistem rekomendasi akan dirancang untuk memberikan rekomendasi yang lebih personal kepada pengguna, mempertimbangkan preferensi dan riwayat bacaan mereka. Hal ini bertujuan untuk meningkatkan kepuasan pengguna dengan menyediakan saran yang lebih relevan dan sesuai dengan minat individu.

- Optimasi Kualitas Rekomendasi:

  Proyek ini juga bertujuan untuk mengoptimalkan kualitas rekomendasi yang diberikan oleh sistem. Ini melibatkan pengembangan model yang mampu mengidentifikasi buku-buku yang paling sesuai dengan preferensi pengguna, serta strategi untuk meningkatkan akurasi dan keberagaman rekomendasi.

  ### Solution statements

- Penerapan Content-Based Filtering (Book Title-Based):

  Dalam rangka menghasilkan rekomendasi yang personal dan relevan, akan diterapkan metode Content-Based Filtering. Pendekatan ini akan mempertimbangkan fitur-fitur konten dari buku, terutama menggunakan Judul buku, untuk menghasilkan rekomendasi yang sesuai dengan preferensi pengguna. Dengan menggunakan informasi dari Judul buku, sistem akan mencari kesamaan antara judul-judul buku yang disukai oleh pengguna untuk menemukan buku-buku yang memiliki kesesuaian tema atau genre yang tinggi. Metode ini dipilih karena cocok untuk menangani kasus di mana preferensi pengguna sangat beragam dan tidak banyak data interaksi pengguna yang tersedia.

- Penggunaan Collaborative Filtering with Popular Based:

  Penggunaan Collaborative Filtering dengan pendekatan Popular Based fokus pada data buku yang paling populer. Metode ini akan memanfaatkan pola perilaku pengguna dan informasi interaksi untuk mengidentifikasi buku-buku yang paling populer di antara pengguna. Pendekatan ini dipilih karena dapat memberikan rekomendasi yang luas dan beragam, yang sesuai dengan preferensi umum dari sebagian besar pengguna.

- Implementasi Collaborative Filtering with User Based:

  Untuk meningkatkan akurasi dan kualitas rekomendasi, Collaborative Filtering dengan pendekatan User Based, menggunakan algoritma RecommenderNet yang akan diimplementasikan dalam sistem. Pendekatan ini akan memanfaatkan teknik *machine learning* yang canggih untuk memodelkan hubungan antara pengguna dan buku-buku yang mereka sukai. RecommenderNet dipilih karena mampu menangani kompleksitas data pengguna dan menghasilkan rekomendasi yang lebih personal dan relevan.

## Data Understanding

Sumber Dataset : https://www.kaggle.com/datasets/arashnic/book-recommendation-dataset/data

Dataset rekomendasi buku dikumpulkan oleh Cai-Nicolas Ziegler dalam penjelajahan selama 4 minggu (Agustus / September 2004) dari komunitas Book-Crossing dengan izin dari Ron Hornbaker, CTO Humankind Systems. Berisi 278.858 *users* (anonim tetapi dengan informasi demografis) memberikan 1.149.780 *rating* (eksplisit / implisit) tentang 271.379 buku.

### Variabel-variabel pada *Recommendation Book Dataset* adalah sebagai berikut:

- Users

  Berisi *User*. Perhatikan bahwa ID *user* (*User-ID*) telah dianonimkan dan dipetakan ke bilangan bulat. Data demografi disediakan (*Location*, *Age*) jika tersedia. Jika tidak, kolom tersebut berisi nilai *NULL*.

- Books

  Buku diidentifikasi berdasarkan ISBN (*International Standard Book Number*) masing-masing. ISBN yang tidak valid telah dihapus dari kumpulan data. Selain itu, beberapa informasi berbasis konten diberikan (*Book-Title*, *Book-Author*, *Year-Of-Publication*, *Publisher*), yang diperoleh dari Amazon Web Services. URL yang tertaut ke gambar sampul juga diberikan, muncul dalam tiga jenis berbeda (*Image-URL-S*, *Image-URL-M*, *Image-URL-L*), yaitu kecil, sedang, besar. URL ini mengarah ke situs web Amazon.

- Ratings

  Berisi informasi tentang *rating* buku. *Rating* (*Book-Rating*) bersifat eksplisit, dinyatakan dalam skala 1-10 (nilai lebih tinggi menunjukkan apresiasi lebih tinggi), atau implisit, dinyatakan dengan 0.

### Exploratory Data Analysis

- Univariate Data Analysis

  - Users

    Tabel 1. Detail Informasi Dataset Users
    | # | Column    | Non-Null Count  | Dtype    |
    | - | --------- | --------------- | -------- |
    | 0 | User-ID   | 278858 non-null | int64    |
    | 1 | Location  | 278858 non-null | object   |
    | 2 | Age       | 168096 non-null | float64  |

    Dalam output info() dari dataset users seperti pada tabel 1, dapat dilihat bahwa dataset ini terdiri dari 278.858 baris dan 3 kolom. Setiap kolom tersebut mencakup informasi tentang User-ID, lokasi pengguna (*Location*), dan usia pengguna (*Age*). Terlihat bahwa kolom User-ID dan Location memiliki 278.858 *non-null values*, artinya tidak ada nilai *NULL* dalam kolom-kolom tersebut. Namun, kolom Age memiliki hanya 168.096 *non-null values*, yang menunjukkan adanya nilai *NULL* atau *missing values* sebanyak 110.762, tetapi hal tersebut dapat diabaikan karena model yang akan dipakai kedepannya tidak berdasarkan kondisi sosial atau demografi dari setiap *user* tersebut. Selain itu, output info() juga memberikan informasi tentang tipe data dari masing-masing kolom, yaitu int64 untuk User-ID, objek (object) untuk Location, dan float64 untuk Age. Selanjutnya adalah melihat 10 penulis teratas berdasarkan jumlah buku.

  - Books

    Tabel 2. Detail Informasi Dataset Books
    | # | Column              | Non-Null Count  | Dtype  |
    | - | ------------------- | --------------- | ------ |
    | 0 | ISBN                | 271360 non-null | object |
    | 1 | Book-Title          | 271360 non-null | object |
    | 2 | Book-Author         | 271358 non-null | object |
    | 3 | Year-Of-Publication | 271360 non-null | object |
    | 4 | Publisher           | 271358 non-null | object |
    | 5 | Image-URL-S         | 271360 non-null | object |
    | 6 | Image-URL-M         | 271360 non-null | object |
    | 7 | Image-URL-L         | 271357 non-null | object |

    Output info() dari dataset books seperti pada tabel 2 menunjukkan bahwa dataset tersebut terdiri dari 271.360 baris dan 8 kolom. Setiap kolom tersebut meliputi informasi seperti ISBN buku, judul buku, penulis buku, tahun penerbitan, penerbit, serta URL gambar untuk ukuran kecil, sedang, dan besar. Dari informasi yang diberikan, dapat dilihat bahwa beberapa kolom memiliki nilai *NULL*, seperti kolom Book-Author dan Publisher, yang masing-masing memiliki 2 nilai *NULL*. Hal tersebut dapat diabaikan karena model yang akan digunakan harus melakukan filtering terlebih dahulu yang dimana terdapat kemungkinan bahwa data kolom yang meiliki nilai *NULL* tersebut tidak diikutsertakan. Semua tipe data dari setiap kolom tersebut adalah *object*, tetapi khusus untuk kolom *'Year_Of_Publication'* tersebut seharusnya tipe datanya adalah *integer*, maka dari itu perlu ditelusuri lebih lanjut tentang data kolom ini yaitu dengan cara mengubah tipe data dari *object* menjadi *integer*. Setelah menemukan error saat mengubah tipe data dari *object* menjadi *integer*, nilai dari kolom *'Year_Of_Publication'* yang tidak sesuai dengan tipe data *integer* akan dihapuskan, setelah dihapus tipe data dari kolom *'Year_Of_Publication'* diubah dari *object* menjadi *integer*.

    ![top-10-authors](https://github.com/maderahano/accom-image/assets/76169846/14ed8825-1c0b-46e4-97ee-6e4f584e62f9)
    Gambar 1. 10 Penulis Teratas Berdasarkan Jumlah Buku Yang Diterbitkan

    Berdasarkan informasi pada Gambar 1, diketahui penulis bernama Agatha Christie paling banyak menulis buku, yakni berjumlah 632 buku. Dari informasi pada Gambar 1 juga terlihat bahwa dataset tersebut berisi beberapa penulis yang telah menulis lebih dari satu judul buku.

  - Ratings

    Tabel 3. Detail Informasi Dataset Ratings
    | # | Column      | Non-Null Count   | Dtype    |
    | - | ----------- | ---------------- | -------- |
    | 0 | User-ID     | 1149780 non-null | int64    |
    | 1 | ISBN        | 1149780 non-null | object   |
    | 2 | Book-Rating | 1149780 non-null | float64  |

    Dalam output info() dari dataset *ratings* seperti pada tabel 3, terdapat informasi bahwa dataset ini terdiri dari 1.149.780 baris dan 3 kolom. Setiap kolom tersebut mencakup informasi tentang User-ID, ISBN buku, dan rating yang diberikan pengguna terhadap buku (*Book-Rating*). Terlihat bahwa semua kolom memiliki 1.149.780 *non-null values*, artinya tidak ada nilai *NULL* dalam dataset ini. Tipe data dari kolom User-ID dan Book-Rating adalah int64, sementara tipe data kolom ISBN adalah objek (*object*). Maka dapat disimpulkan bahwa tipe data setiap kolom tersebut sudah sesuai dengan konteksnya dan tidak ada nilai yang *NULL* yang menandakan bahwa tidak perlu adanya modifikasi isi data dari dataset *ratings*. Selanjutnya adalah melihat 10 buku paling populer dan 10 user paling berpengalaman.

    ![top-10-populer-books](https://github.com/maderahano/accom-image/assets/76169846/8fd84715-414b-4a53-92dc-8abb4abce09b)
    Gambar 2. 10 Buku Populer Berdasarkan Jumlah Rating yang Diterima

    Analisis dari Gambar 2 menunjukkan bahwa buku dengan judul Wild Animus memperoleh jumlah rating terbanyak, mencapai total 2502 rating. Selain itu, data pada Gambar 2 juga menunjukkan bahwa dalam dataset ratings dan books, beberapa buku telah menerima lebih dari 250 rating.

    ![top-10-experienced-users](https://github.com/maderahano/accom-image/assets/76169846/e9f85c50-e879-4b9b-a97e-520eea64d947)
    Gambar 3. 10 Pengguna Berpengalaman Berdasarkan Jumlah Rating yang Diberikan

    Berdasarkan data pada Gambar 3, dapat disimpulkan bahwa pengguna dengan ID 11676 memberikan jumlah rating terbanyak kepada buku, yakni sebanyak 13.602 rating. Analisis pada Gambar 3 juga menunjukkan bahwa dataset ratings dan users mengungkap bahwa setiap pengguna telah memberikan rating kepada buku-buku dengan jumlah yang besar. Oleh karena itu, dataset users tersebut merupakan pilihan yang sesuai untuk digunakan dalam pengembangan Model *Collaborative Filtering*.

## Data Preparation

### Data Preprocessing

- Menggabungkan Data antara *Books* dengan *Ratings*

  Dengan menggunakan fungsi pd.merge() dari library Pandas, kedua dataframe yaitu dataframe ratings dan dataframe books digabungkan berdasarkan kolom ISBN dari kedua dataframe tersebut sebagai kunci penggabungan. Penggunaan parameter how='left' menandakan bahwa kita ingin mempertahankan semua nilai dari dataframe ratings dan mencocokkan data buku dari dataframe books jika ada, sementara jika tidak ada, akan menghasilkan nilai *NULL* atau *NaN*. Hasil penggabungan disimpan dalam variabel new_data, yang nantinya akan berisi gabungan antara informasi rating buku dengan detail buku yang sesuai berdasarkan ISBN. Penggunaan variabel new_data ini, akan digunakan pada saat menggunakan model C*ontent-Based Filtering* dan *Collaborative Filtering* dengan *Popular Based*.

### Data Preparation for Model Development Content-Based Filtering

1. Mengatasi Missing Value

    Langkah pertama dalam tahap *Data Preparation* untuk pengembangan model *Content-Based Filtering* adalah mengatasi nilai yang hilang atau *missing value* dalam *dataset*. Untuk melakukan hal ini, digunakan kode yang terdiri dari dua bagian. Bagian pertama adalah dengan menggunakan fungsi isnull().sum() pada dataframe new_data untuk mengecek jumlah nilai yang hilang dalam setiap kolom. Ini memberikan pemahaman yang jelas tentang seberapa banyak data yang hilang dalam setiap fitur. Kemudian, untuk membersihkan atau menghapus nilai-nilai yang hilang dari *dataset*, digunakan fungsi dropna(). Dalam kode ini, seluruh *dataset* yang sudah dibersihkan dari nilai-nilai yang hilang disimpan dalam variabel baru yaitu all_new_data_clean.

2. Standarisasi

    Langkah selanjutnya dalam proses *Data Preparation* adalah standarisasi. Pertama, data all_new_data_clean diurutkan berdasarkan ISBN dan disimpan dalam variabel fix_data. Karena tidak ada data yang cacat make selanjutnya, data yang sudah diurutkan tersebut disimpan dalam variabel preparation, dan kemudian data duplikat berdasarkan ISBN dihapus. Setelah itu, kolom-kolom tertentu seperti 'ISBN', 'Book_Title', 'Book_Author', 'Year_Of_Publication', 'Publisher', dan URL gambar dari dataset yang sudah dipersiapkan dikonversi menjadi list terpisah. Selanjutnya, list tersebut digunakan untuk membuat dataframe baru yang bernama books_new, yang berisi informasi tentang buku-buku yang telah dipersiapkan. Terakhir, hanya 25.000 data pertama dari books_new yang dipertahankan untuk analisis lebih lanjut. Hal tersebut dilakukan karena jumlah dataset terlalu besar yaitu sebanyak 270.144 data setelah melakukan pengurutan data dan menghapus duplikasi data, serta alokasi memori yang digunakan akan sangat besar untuk memproses seluruh data dalam model development

### Data Preparation for Model Development Collaborative Filtering with Popular Based

1. Filter Data Buku Populer

    Dalam tahap persiapan data untuk pengembangan model *Collaborative Filtering* dengan *Popular Based*, langkah pertama yang dilakukan adalah melakukan filter terhadap buku-buku populer. Proses ini dilakukan dengan mengelompokkan dataset new_data berdasarkan judul buku, kemudian menghitung jumlah total rating yang diberikan oleh pengguna (Count_Rating) dan rata-rata rating dari setiap judul buku (Average_Rating). Setelah itu, kedua data tersebut digabungkan menjadi satu dataframe menggunakan kolom 'Book_Title' sebagai kunci penggabungan. Selanjutnya, dilakukan filter untuk memilih 50 buku yang paling populer berdasarkan rata-rata rating tertinggi, dengan syarat minimal memiliki 250 rating yang diberikan oleh pengguna. Hasilnya adalah dataframe popular_book_data, yang berisi informasi tentang 50 buku paling populer berdasarkan kriteria tersebut.

2. Filter Data User Berpengalaman

    Langkah selanjutnya dalam tahap persiapan data untuk pengembangan model *Collaborative Filtering* adalah melakukan filter terhadap data pengguna berpengalaman. Proses ini dimulai dengan mengelompokkan dataset new_data berdasarkan kolom 'User_ID', kemudian menghitung jumlah buku yang pernah diberi rating oleh setiap pengguna. Hasilnya disimpan dalam variabel user_rating_count, yang merupakan sebuah series yang menampilkan jumlah rating yang diberikan oleh setiap pengguna. Selanjutnya, kondisi boolean dibuat dengan membandingkan jumlah rating setiap pengguna dengan 200. Nilai *True* yang dihasilkan dari kondisi ini menunjukkan bahwa pengguna tersebut telah memberi rating lebih dari 200 buku, sementara nilai *False* menunjukkan sebaliknya. Variabel is_experienced_users digunakan untuk menyimpan hasil kondisi boolean tersebut. Pengguna yang berpengalaman kemudian difilter berdasarkan kondisi *True*, sehingga hanya indeks 'User_ID' dari pengguna berpengalaman yang disimpan dalam variabel experienced_users. Terakhir, data diproses kembali untuk menyaring hanya rating dari pengguna berpengalaman, yang dihasilkan dari dataframe new_data dan disimpan dalam variabel filtered_data.

3. Filter Data Buku Berdasarkan Dari Data User Berpengalaman dan Buku Populer

    Langkah selanjutnya dalam tahap persiapan data untuk pengembangan model *Collaborative Filtering* adalah melakukan filter terhadap data buku berdasarkan informasi dari data pengguna berpengalaman dan buku populer. Proses ini dimulai dengan mengelompokkan dataset filtered_data berdasarkan kolom 'Book_Title', kemudian menghitung jumlah rating yang diberikan untuk setiap judul buku. Hasilnya disimpan dalam variabel book_rating_count, yang merupakan sebuah series yang menampilkan jumlah rating yang diberikan untuk setiap judul buku. Selanjutnya, kondisi boolean dibuat dengan membandingkan jumlah rating setiap buku dengan 50. Nilai *True* yang dihasilkan dari kondisi ini menunjukkan bahwa buku tersebut telah diberi rating oleh lebih dari 50 pengguna, sementara nilai *False* menunjukkan sebaliknya. Variabel is_popular_book digunakan untuk menyimpan hasil kondisi boolean tersebut. Buku-buku populer kemudian difilter berdasarkan kondisi *True*, sehingga hanya indeks 'Book_Title' dari buku-buku populer yang disimpan dalam variabel popular_books. Terakhir, data diproses kembali untuk menyaring hanya judul buku dari buku-buku populer, yang dihasilkan dari dataframe filtered_data dan disimpan dalam variabel final_data.

4. Pivot Dataset

    Langkah terakhir dalam tahap persiapan data untuk pengembangan model *Collaborative Filtering* adalah melakukan pivot dataset. Proses ini melibatkan pengelompokan DataFrame final_data berdasarkan 'Book_Title' dan 'User_ID', kemudian menghitung nilai rata-rata untuk setiap kombinasi buku dan pengguna. Hasilnya adalah sebuah tabel pivot yang memiliki buku sebagai baris dan pengguna sebagai kolom. Variabel pivot_data digunakan untuk menyimpan tabel pivot ini. Selanjutnya, nilai yang hilang dalam tabel pivot diisi dengan angka nol menggunakan fungsi fillna().

### Data Preparation for Model Development Collaborative Filtering with User Based

1. Encoding User ID

    Dalam tahap *Data Preparation* untuk pengembangan model *Collaborative Filtering* dengan *User Based*, langkah pertama adalah melakukan encoding terhadap User ID. Proses dimulai dengan mengambil nilai unik dari kolom User_ID dalam dataset collab_ratings, yang telah diambil dari dataset ratings yang terdiri dari 25.000 data pertama yang dipertahankan untuk analisis lebih lanjut. Nilai unik dari dataset collab_ratings diubah menjadi list tanpa nilai yang sama, yang kemudian disimpan dalam variabel user_ids. Selanjutnya, encoding dilakukan terhadap User_ID menggunakan dictionary comprehension, di mana setiap nilai User_ID dienkripsi menjadi nilai yang sesuai dengan indeksnya dalam list user_ids. Hasil encoding ini disimpan dalam variabel user_to_user_encoded. Langkah selanjutnya adalah melakukan decoding dari angka kembali ke User_ID, dengan membalikkan kunci dan nilai dalam dictionary user_to_user_encoded. Hasilnya disimpan dalam variabel user_encoded_to_user.

2. Encoding ISBN

    Langkah selanjutnya dalam tahap persiapan data untuk pengembangan model *Collaborative Filtering* dengan *User Based* adalah melakukan encoding terhadap ISBN. Proses ini dimulai dengan mengambil nilai unik dari kolom ISBN dalam dataset collab_ratings. Nilai unik dari dataset ini diubah menjadi list tanpa nilai yang sama, yang kemudian disimpan dalam variabel isbn_ids. Selanjutnya, dilakukan encoding terhadap ISBN menggunakan dictionary comprehension, di mana setiap nilai ISBN dienkripsi menjadi nilai yang sesuai dengan indeksnya dalam list isbn_ids. Hasil encoding ini disimpan dalam variabel isbn_to_isbn_encoded. Langkah terakhir adalah melakukan decoding dari angka kembali ke ISBN, dengan membalikkan kunci dan nilai dalam dictionary isbn_to_isbn_encoded. Hasilnya disimpan dalam variabel isbn_encoded_to_isbn.

3. Mapping

    Langkah terakhir dalam *Collaborative Filtering* dengan M*emory Based* adalah melakukan *Mapping*. Proses ini melibatkan dua langkah utama: pertama, melakukan pemetaan User_ID ke dataframe collab_ratings['user'] dan kedua, melakukan pemetaan ISBN ke dataframe collab_ratings['book_title']. Pemetaan dilakukan dengan menggunakan dictionary yang telah dibuat sebelumnya untuk mengenkripsi User_ID dan ISBN ke nilai yang sesuai. Setelah itu, jumlah pengguna dan judul buku dihitung dengan menggunakan fungsi len() dan disimpan dalam variabel num_users dan num_book_titles, serta nilai rating diubah menjadi tipe data float32. Selain itu, nilai minimum dan maksimum rating juga ditentukan untuk dataset dengan menggunakan fungsi min() dan max() lalu disimpan dalam variabel min_rating dan max_rating.

## Modeling

### Model Development Content-Based Filtering

*Content-Based Filtering* merupakan pendekatan dalam sistem rekomendasi yang memanfaatkan informasi atau "konten" dari item atau pengguna untuk membuat rekomendasi. Konsep utamanya adalah mencocokkan preferensi pengguna dengan karakteristik atau konten item yang telah dilihat atau disukai oleh pengguna sebelumnya. Misalnya, jika pengguna menyukai atau telah membeli buku berjudul "The Foxman" yang ditulis oleh "Gary Paulsen", sistem akan mencari buku lain dengan fitur serupa dan merekomendasikannya dalam bentuk rekomendasi top-N kepada pengguna.

Dalam pengembangan model, dilakukan pencarian representasi fitur penting dari setiap judul buku menggunakan Vectorizer TF-IDF (Term Frekuensi-Inverse Document Frekuensi), alat yang mengubah dokumen teks menjadi vektor berdasarkan nilai TF-IDF dari setiap kata dalam dokumen. Representasi ini digunakan untuk mencari fitur penting dari setiap judul buku berdasarkan nama penulis pada model yang dikembangkan dengan *Content-Based Filtering*, menggunakan fungsi tfidfvectorizer() dari *library* Sklearn. Selain itu, digunakan teknik cosine similarity untuk menghitung derajat kemiripan antara judul buku. Metode ini mengukur kemiripan antara dua vektor dalam ruang berdimensi tinggi, menggunakan fungsi cosine_similarity dari *library* Sklearn. Dengan teknik-teknik ini, dapat dikembangkan model *Content-Based Filtering* untuk memberikan rekomendasi buku yang lebih tepat sesuai dengan preferensi pengguna.

#### Kelebihan *Model Development Content-Based Filtering*:

- Personalisasi: Model ini memberikan rekomendasi yang disesuaikan dengan preferensi individu pengguna berdasarkan fitur-fitur item yang telah disukai sebelumnya.

- Tidak Bergantung pada Data Pengguna Lain: Model ini tidak memerlukan informasi tentang pengguna lain atau aktivitas pengguna lain untuk memberikan rekomendasi.

- Interpretabilitas: Model ini bisa lebih mudah diinterpretasikan karena rekomendasi didasarkan pada fitur-fitur yang dapat dimengerti manusia, seperti judul, genre, atau pengarang.

#### Kekurangan *Model Development Content-Based Filtering*:

- Keterbatasan Dalam Diversitas: Model ini cenderung merekomendasikan item yang serupa dengan item yang sudah disukai pengguna sebelumnya, yang bisa mengurangi keragaman rekomendasi.

- Keterbatasan Fitur: Kualitas rekomendasi sangat tergantung pada kualitas fitur yang digunakan untuk mewakili item. Fitur yang kurang informatif atau tidak relevan dapat menghasilkan rekomendasi yang tidak akurat.

- Keterbatasan dalam Memodelkan Perubahan Preferensi: Model ini cenderung kurang efektif dalam menangani perubahan preferensi pengguna dari waktu ke waktu, karena hanya menggunakan informasi tentang item yang telah dinilai sebelumnya.

#### Hasil Model Development Content-Based Filtering

Untuk mendapatkan hasil *model development content-based filtering*, sebuah fungsi yang disebut book_recommendations akan dibuat. Fungsi ini akan memiliki beberapa parameter sebagai berikut:

- judul_buku: merupakan nama judul buku yang akan digunakan sebagai indeks kesamaan dalam dataframe.

- similarity_data: adalah kerangka data yang menyimpan informasi tentang kesamaan yang telah ditentukan sebelumnya.

- items: berisi nama-nama dan fitur-fitur yang akan digunakan untuk mendefinisikan kesamaan antara judul buku, dalam hal ini, 'judul_buku' dan 'penulis_buku'.

- k: adalah jumlah rekomendasi teratas (top-N) yang akan diberikan oleh sistem rekomendasi. Secara default, nilai k diatur ke 5.

Selanjutnya, akan dilakukan percobaan terhadap sistem rekomendasi buku menggunakan metode *Content-Based Filtering*. Contoh yang akan dievaluasi adalah judul buku 'The Foxman'. Sebelum melakukan percobaan, diperlukan informasi tambahan mengenai buku tersebut, seperti nama pengarang, tahun publikasi, dan detail lain yang dapat mempengaruhi proses rekomendasi.

```
test_judul_buku = 'The Foxman'

data_content[data_content.book_title.eq(test_judul_buku)]
```
Tabel 4. Detail Informasi dari Judul Buku The Foxman
|       | isbn       | book_title | book_author  |
| ----- | ---------- | ---------- | ------------ |
| 18773	| 0140343113 | The Foxman | Gary Paulsen |

Perlu diketahui bahwa judul buku 'The Foxman' ditulis oleh 'Gary Paulsen'. Sekarang, gunakan fungsi book_recommendation untuk mendapatkan rekomendasi berdasarkan judul buku ini. Berikut adalah hasil Top 5 Rekomendasi Buku dari sistem:

Tabel 5. Hasil Rekomendasi dari Judul Buku The Foxman
|   | book_title                       | book_author  |
| - | -------------------------------- | ------------ |
| 0	| Dogsong                          | Gary Paulsen |
| 1	| Tiltawhirl John	                 | Gary Paulsen |
| 2	| The Beet Fields (Definitions S.) | Gary Paulsen |
| 3	| Hatchet	Gary Paulsen	           | Gary Paulsen |
| 4	| Hatchet	Gary Paulsen	           | Gary Paulsen |

*Untuk kolom image_url_l tidak ditulis karena terlalu panjang. 

### Model Development Collaborative Filtering with Popular Based

*Collaborative Filtering* merupakan salah satu pendekatan dalam sistem rekomendasi yang memproyeksikan preferensi pengguna terhadap item berdasarkan informasi dari pengguna lain (kolaborasi). Tahapan utama dalam pengembangan model ini melibatkan dua proses utama: filter data dan pencarian kemiripan.

Dalam pengembangan model *Collaborative Filtering with Popular Based*, tahap pertama adalah filter data dan tahap kedua adalah pencarian kemiripan. Proses filter data telah dilakukan pada tahap *data preparation*, di mana data rating yang diberikan oleh pengguna terhadap buku dikumpulkan dan diproses untuk memastikan keakuratan hasil rekomendasi. Selanjutnya, dalam tahap pencarian kemiripan, proyek ini menggunakan metode cosine similarity. Teknik ini mengukur kemiripan antara dua vektor dalam ruang berdimensi tinggi, di mana representasi vektor mewakili pola rating antara user dengan item seperti buku. Dengan menggunakan cosine similarity, model dapat menemukan item yang memiliki pola rating serupa, sehingga dapat memberikan rekomendasi yang sesuai dengan preferensi pengguna tanpa memerlukan informasi eksplisit tentang item atau pengguna.

#### Kelebihan *Collaborative Filtering with Popular Based*:

- Sederhana dan Mudah diimplementasikan: Collaborative Filtering berbasis popularitas adalah salah satu metode yang paling mudah dan sederhana dalam sistem rekomendasi. Pendekatannya didasarkan pada popularitas item, yang membuatnya mudah diimplementasikan tanpa memerlukan analisis yang kompleks atau data rating pengguna.

- Efektif untuk Item Populer: Metode ini sangat efektif untuk merekomendasikan item yang sudah populer dan memiliki banyak interaksi atau rating dari pengguna. Ini karena rekomendasi didasarkan pada popularitas item, yang cenderung menarik bagi sebagian besar pengguna.

- Tidak Memerlukan Informasi Pengguna: Collaborative Filtering berbasis popularitas tidak memerlukan informasi tentang preferensi atau perilaku pengguna. Ini membuatnya cocok untuk digunakan dalam kasus-kasus di mana data pengguna tidak tersedia atau terbatas.

#### Kekurangan *Collaborative Filtering with Popular Based*:

- Kurang Personalisasi: Salah satu kelemahan utama dari Collaborative Filtering berbasis popularitas adalah kurangnya personalisasi dalam rekomendasi. Karena hanya mempertimbangkan popularitas item secara keseluruhan, rekomendasi yang dihasilkan mungkin tidak sesuai dengan preferensi atau kebutuhan spesifik dari setiap pengguna.

- Tidak Efektif untuk Item Niche atau Kurang Populer: Metode ini cenderung tidak efektif untuk merekomendasikan item yang kurang populer atau niche. Item-item seperti itu mungkin tidak mendapatkan perhatian yang cukup dalam metode ini karena fokus pada popularitas umum.

- Rentan terhadap Bias Populeritas: Collaborative Filtering berbasis popularitas rentan terhadap bias popularitas, di mana item-item yang sudah populer cenderung mendapatkan lebih banyak eksposur dan rekomendasi, sementara item yang kurang populer mungkin terabaikan.

- Tidak Efektif dalam Memecahkan Masalah Cold Start: Metode ini tidak efektif dalam menangani masalah cold start, terutama saat pertama kali diluncurkan atau ketika item baru ditambahkan ke dalam sistem. Ini karena membutuhkan jumlah interaksi yang cukup untuk membuat item menjadi populer dalam sistem.

#### Hasil Model Development Collaborative Filtering with Popular Based

Untuk mendapatkan hasil *model development collaborative filtering with popular based*, sebuah fungsi yang disebut recommend_book akan dibuat. Fungsi ini memiliki satu parameter yaitu:

- book_name: merupakan nama judul buku yang akan digunakan sebagai indeks kesamaan dalam dataframe.

Selanjutnya, akan dilakukan percobaan terhadap sistem rekomendasi buku menggunakan metode *Collaborative Filtering with Popular Based*. Contoh yang akan dievaluasi adalah judul buku 'You Belong To Me'. Sebelum melakukan percobaan, diperlukan informasi tambahan mengenai buku tersebut, seperti nama pengarang, tahun publikasi, dan detail lain yang dapat mempengaruhi proses rekomendasi.

Tabel 6. Detail Informasi dari Judul Buku You Belong To Me
|       | ISBN       | Book_Title       | book_author        |
| ----- | ---------- | ---------------- | ------------------ |
| 14438	| 0671004549 | You Belong To Me | Mary Higgins Clark |

Perlu diketahui bahwa judul buku 'You Belong To Me' ditulis oleh 'Mary Higgins Clark'. Sekarang, gunakan fungsi recommend_book untuk mendapatkan rekomendasi berdasarkan judul buku ini. Berikut adalah hasil Buku populer yang direkomendasikan oleh sistem:

Tabel 7. Hasil Rekomendasi dari Judul Buku You Belong To Me
|   | book_title                  | book_author        |
| - | --------------------------- | ------------------ |
| 0	| Loves Music, Loves to Dance | Mary Higgins Clark |
| 1	| I'll Be Seeing You          | Mary Higgins Clark |
| 2	| Before I Say Good-Bye       | Mary Higgins Clark |
| 3	| Daddy's Little Girl         | Mary Higgins Clark |

*Untuk kolom image_url_l tidak ditulis karena terlalu panjang. 

### Model Development Collaborative Filtering with User Based

*Collaborative Filtering* merupakan salah satu pendekatan dalam sistem rekomendasi yang memproyeksikan preferensi pengguna terhadap item berdasarkan informasi dari pengguna lain (kolaborasi). Konsep utama di balik pendekatan ini adalah bahwa pengguna dengan preferensi serupa di masa lalu cenderung memiliki preferensi serupa terhadap item di masa mendatang. Dalam proyek ini, proyek ini akan mengembangkan model *Collaborative Filtering* berdasarkan kesamaan pengguna (*User-Based Collaborative Filtering*). Pengembangan model Collaborative Filtering pada proyek ini bertujuan untuk merekomendasikan sejumlah judul buku yang sesuai dengan preferensi pengguna berdasarkan rating yang diberikan sebelumnya. Dari data rating pengguna, proyek ini akan mengidentifikasi dan merekomendasikan judul buku serupa yang belum dibaca atau dibeli oleh pengguna.

Dalam pengembangan model *Collaborative Filtering with User Based*, tahap pertama adalah tapa persiapan data yang sudah dijelaskan di bagian *Data Preparation for Model Development Content-Based Filtering*. Setelah tahap persiapan data selesai, langkah berikutnya adalah membagi data menjadi data latih dan data validasi, kemudian melanjutkan dengan proses pelatihan model. Dalam proses pelatihan ini, model menghitung skor kecocokan antara pengguna dan judul buku menggunakan teknik embedding. Pertama, proyek ini melakukan embedding pada data pengguna dan judul buku, kemudian melakukan operasi perkalian titik antara embedding pengguna dan judul buku. proyek ini juga menambahkan bias untuk setiap pengguna dan judul buku. Skor kecocokan diatur dalam skala [0,1] menggunakan fungsi aktivasi sigmoid. Model proyek ini dibangun dengan menggunakan kelas RekomendasierNet menggunakan kelas Model Keras. Kode untuk kelas RekomendasierNet ini terinspirasi dari tutorial di situs Keras dengan beberapa penyesuaian agar sesuai dengan kasus proyek ini. Model ini akan menggunakan Binary Crossentropy untuk menghitung fungsi kerugian, Adam (Adaptive Moment Estimation) sebagai pengoptimal, dan Root Mean Squared Error (RMSE) sebagai metrik evaluasi.

#### Kelebihan *Collaborative Filtering with User Based*:

- Personalisasi yang Tinggi: Collaborative Filtering memungkinkan sistem rekomendasi untuk memberikan rekomendasi yang sangat personal bagi setiap pengguna. Ini karena rekomendasi dibuat berdasarkan pada preferensi pengguna serta pola perilaku dari pengguna lain yang memiliki preferensi serupa.

- Tidak Memerlukan Informasi Eksternal: Metode ini hanya memerlukan data rating yang diberikan oleh pengguna, tanpa memerlukan informasi tambahan tentang item yang direkomendasikan. Ini membuatnya lebih mudah untuk diterapkan dan diintegrasikan dengan data yang sudah ada.

- Efektif untuk Item Baru: Collaborative Filtering dapat memberikan rekomendasi yang relevan untuk item baru yang belum memiliki banyak data rating. Hal ini karena rekomendasi dibuat berdasarkan pada pola perilaku pengguna yang serupa, bukan hanya berdasarkan pada karakteristik item.

#### Kekurangan *Collaborative Filtering with User Based*:

- Cold Start Problem: Collaborative Filtering cenderung mengalami masalah cold start, terutama saat pertama kali diluncurkan atau ketika item baru ditambahkan ke dalam sistem. Ini karena sistem memerlukan data rating yang cukup untuk membuat rekomendasi yang akurat.

- Sparsity of Data: Collaborative Filtering juga rentan terhadap masalah kerapuhan data (data sparsity), terutama saat jumlah pengguna dan item yang besar. Semakin sedikit interaksi (rating) yang ada antara pengguna dan item, semakin sulit bagi sistem untuk membuat rekomendasi yang akurat.

- Over-Specialization: Ada risiko bahwa Collaborative Filtering cenderung menghasilkan rekomendasi yang terlalu spesifik atau terbatas, terutama saat tidak ada banyak variasi dalam data rating. Ini dapat mengakibatkan pengguna hanya menerima rekomendasi yang mirip dengan preferensi mereka yang sudah ada, tanpa mendapatkan saran baru atau variasi yang signifikan.

- Scalability: Dalam skala besar, Collaborative Filtering dapat menjadi sulit untuk diimplementasikan karena memerlukan perhitungan yang kompleks dan membutuhkan sumber daya komputasi yang besar, terutama saat jumlah pengguna dan item yang besar.

#### Hasil Model Development Collaborative Filtering with User Based

Untuk mendapatkan rekomendasi judul buku, langkah pertama adalah mengambil sampel acak pengguna. Kemudian, dibuat variabel book_not_read, yang merupakan daftar buku yang belum pernah dibaca atau dibeli oleh pengguna. Variabel ini akan digunakan sebagai judul buku yang direkomendasikan oleh sistem. Selain itu, variabel book_not_visited diperoleh dengan menggunakan operator NOT bitwise (~) pada variabel book_read_by_user. Variabel ini menunjukkan daftar buku yang belum pernah dikunjungi oleh pengguna.

Selanjutnya untuk mendapatkan rekomendasi judul buku, gunakan fungsi model.predict() dari *library* Keras. Dan berikut adalah hasil Top 10 Rekomendasi Buku dari sistem:

```
Showing recommendations for users: 3363
===========================
Book with high ratings from user
--------------------------------
```
Tabel 9. Buku dengan peringkat tinggi dari pengguna
|   | book_title                                         | book_author |
| - | -------------------------------------------------- | ----------- |
| 0	| Getting Over It                                    | Anna Maxted |
| 1	| Princess in the Spotlight (The Princess Diarie...) | Meg Cabot   |

```
--------------------------------
Top 10 book recommendation
--------------------------------
```
Tabel 8. Top 10 Buku yang Direkomendasikan oleh Sistem
|   | book_title                                        | book_author        |
| - | ------------------------------------------------- | ------------------ |
| 0	| Small Wonder: Essays                              | Barbara Kingsolver |
| 1	| To the Heart of the Nile : Lady Florence Baker... | Pat Shipman        |
| 2	| To Kill a Mockingbird                             | Harper Lee         |
| 3	| American Pie : A Novel                            | Michael Lee West   |
| 4	| Joke                                              | Milan Kundera      |
| 5	| Sociolinguistics: An Introduction to Language ... | Peter Trudgill     |
| 6	| The Grapes of Wrath: John Steinbeck Centennial... | John Steinbeck     |
| 7	| Last Watch Of The Night: Essays Too Personal a... | Paul Monette       |
| 8	| The Whale Rider                                   | Witi Ihimaera      |
| 9	| The Pilgrim's Progress (The World's Classics)     | John Bunyan        |

## Evaluation

### Model Evaluasi dengan Content-Based Filtering

Metrik evaluasi yang digunakan dalam proyek ini untuk model *Content-Based Filtering* adalah metrik Precision. Metrik presisi (precision) adalah salah satu metrik evaluasi yang digunakan untuk mengukur seberapa banyak item yang diprediksi secara benar oleh model terhadap total item yang diprediksi sebagai positif. Dalam konteks sistem rekomendasi, presisi mengukur proporsi item yang relevan yang diprediksi sebagai relevan oleh model terhadap total item yang diprediksi sebagai relevan. Secara matematis, presisi dapat dihitung dengan rumus:

$$
  P = \frac{x}{n}\
$$

- x = item rekomendasi yang relevan
- n = jumlah item rekomendasi


Dalam analisis tabel 4 dan tabel 5, tabel 4 memberikan rincian tentang judul buku dan nama pengarang. Sementara itu, tabel 5 menampilkan hasil rekomendasi buku berdasarkan judul buku dari tabel 4, bergantung pada nama pengarangnya. Dengan demikian, dapat disimpulkan bahwa nilai x adalah 5 karena semua hasil rekomendasi pada tabel 5 dalam kolom nama pengarangnya sama dengan nama pengarang yang ada di tabel 4. Sementara itu, n adalah 5 karena jumlah buku yang ingin direkomendasikan adalah 5. Oleh karena itu, perhitungannya sebagai berikut:

$$
  P = \frac{5}{5}\ = 1
$$

Berdasarkan hasil perhitungan, diperoleh nilai presisi sebesar 1. Hal ini menunjukkan bahwa semua prediksi model positif benar, dan tidak ada positif palsu. Dengan kata lain, model secara sempurna mengidentifikasi item yang relevan untuk direkomendasikan kepada pengguna. Hasil presisi yang mencapai 1 mengindikasikan kinerja yang sangat baik dari sistem rekomendasi, menunjukkan bahwa model dapat memberikan rekomendasi dengan akurasi yang tinggi sesuai dengan preferensi pengguna.

### Model Evaluasi Collaborative Filtering with Popular Based

Metrik evaluasi yang digunakan dalam proyek ini untuk model *Collaborative Filtering with Popular Based* adalah Precision. Metrik presisi (precision) adalah salah satu metrik evaluasi yang digunakan untuk mengukur seberapa banyak item yang diprediksi secara benar oleh model terhadap total item yang diprediksi sebagai positif. Dalam konteks sistem rekomendasi, presisi mengukur proporsi item yang relevan yang diprediksi sebagai relevan oleh model terhadap total item yang diprediksi sebagai relevan. Secara matematis, presisi dapat dihitung dengan rumus:

$$
  P = \frac{x}{n}\
$$

- x = item rekomendasi yang relevan
- n = jumlah item rekomendasi

Dalam analisis tabel 6 dan tabel 7, tabel 6 memberikan rincian tentang judul buku dan nama pengarang. Sementara itu, tabel 7 menampilkan hasil rekomendasi buku berdasarkan judul buku dari tabel 6, bergantung pada nama pengarangnya. Dengan demikian, dapat disimpulkan bahwa nilai x adalah 4 karena semua hasil rekomendasi pada tabel 7 dalam kolom nama pengarangnya sama dengan nama pengarang yang ada di tabel 6. Sementara itu, n adalah 4 karena hasil jumlah buku yang direkomendasikan adalah 4. Oleh karena itu, perhitungannya sebagai berikut:

$$
  P = \frac{4}{4}\ = 1
$$

Berdasarkan hasil perhitungan, diperoleh nilai presisi sebesar 1. Hal ini menunjukkan bahwa semua prediksi model positif benar, dan tidak ada positif palsu. Dengan kata lain, model secara sempurna mengidentifikasi item yang relevan untuk direkomendasikan kepada pengguna. Hasil presisi yang mencapai 1 mengindikasikan kinerja yang sangat baik dari sistem rekomendasi, menunjukkan bahwa model dapat memberikan rekomendasi dengan akurasi yang tinggi sesuai dengan preferensi pengguna.

### Model Evaluasi Collaborative Filtering with User Based

Dalam proses pelatihan model *Collaborative Filtering with User Based* pada tahap pemodelan, metrik evaluasi yang digunakan adalah *Root Mean Squared Error* (RMSE). RMSE adalah metrik umum yang digunakan untuk mengukur kualitas prediksi model dengan membandingkan nilai prediksi dengan nilai sebenarnya. Dalam konteks pemfilteran kolaboratif, RMSE berguna untuk mengevaluasi seberapa baik model dapat memprediksi preferensi pengguna terhadap item.

Hasil dari proses pelatihan model memberikan informasi RMSE pada data pelatihan dan validasi. Untuk memvisualisasikan proses pelatihan model, digunakan proses plotting menggunakan matplotlib. Untuk Hasilnya dapat dilihat pada Gambar 4.

![books-evaluation-metric](https://github.com/maderahano/accom-image/assets/76169846/4e71d2db-14cb-4176-8052-c8dcecb633b5)
Gambar 4. Matrix Evaluasi RMSE Pada Model *Collaborative Filtering with User Based*

Hasil visualisasi metrik evaluasi RMSE untuk model Collaborative Filtering with User Based pada Gambar 4 menunjukkan bahwa model tersebut mencapai konvergensi setelah sekitar 100 epoch. Plot metrik menunjukkan bahwa model memberikan nilai RMSE yang relatif kecil selama proses pelatihan, menunjukkan kemajuan yang stabil. Dari proses tersebut, diperoleh nilai error akhir sebesar 0.1164 untuk data pelatihan dan 0.3613 untuk data validasi. Nilai RMSE yang rendah pada data pelatihan menandakan kemampuan model dalam memperkirakan nilai-nilai yang sebenarnya dengan akurasi tinggi. Namun, perbedaan yang signifikan antara nilai RMSE pada data pelatihan dan validasi menunjukkan adanya overfitting pada model. Ini mengindikasikan bahwa model terlalu disesuaikan dengan data pelatihan dan tidak dapat secara efektif menggeneralisasi pada data baru. Untuk mengatasi overfitting, dapat dilakukan dengan menggunakan teknik seperti regularisasi, cross-validation, atau penggunaan dataset yang lebih besar untuk pelatihan. Dengan langkah-langkah ini, model dapat meningkatkan kemampuannya dalam memberikan rekomendasi yang lebih akurat dan dapat diandalkan.

## Conclusion

Berdasarkan hasil evaluasi yang diberikan, terdapat perbedaan signifikan dalam kinerja antara model-model yang telah diuji. Model Content-Based Filtering dan Collaborative Filtering with Popular Based menunjukkan hasil evaluasi yang sangat baik, dengan nilai sempurna untuk Precision (1.0). Hal ini menandakan bahwa kedua model ini mampu memberikan prediksi yang sempurna dan konsisten dengan preferensi pengguna terhadap item. Meskipun demikian, perlu dicatat bahwa hasil evaluasi yang sempurna seperti ini mungkin terlalu ideal dan kurang realistis, terutama dalam konteks pengalaman dunia nyata.

Sementara itu, model Collaborative Filtering with User Based dievaluasi menggunakan nilai RMSE, dengan hasil 0.1164 untuk data pelatihan dan 0.3613 untuk data validasi. Meskipun nilai RMSE yang rendah menunjukkan bahwa model ini mampu memberikan prediksi yang dekat dengan nilai sebenarnya, model berbasis kolaboratif masih memiliki ruang untuk peningkatan dalam menyesuaikan rekomendasinya dengan preferensi pengguna secara lebih akurat.

Dengan demikian, kesimpulan proyek ini mungkin adalah bahwa model berbasis konten memiliki kinerja yang lebih baik dalam memberikan prediksi yang sempurna, sementara model berbasis kolaboratif masih memiliki potensi untuk ditingkatkan dalam menyesuaikan rekomendasinya dengan preferensi pengguna secara lebih akurat. Sebagai rekomendasi lanjutan, pengembangan lebih lanjut pada model berbasis kolaboratif dapat dilakukan dengan mempertimbangkan variasi dalam penggunaan teknik dan strategi yang lebih canggih dalam menangani kasus yang lebih kompleks.

