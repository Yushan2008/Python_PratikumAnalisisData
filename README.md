Analisis Penjualan E-commerce
Proyek ini menganalisis data penjualan e-commerce untuk mengidentifikasi pola, memahami perilaku pelanggan, dan memberikan rekomendasi berbasis data untuk meningkatkan kinerja bisnis.

1. Business Question
Analisis ini bertujuan untuk menjawab beberapa pertanyaan kunci, antara lain:

Bagaimana tren penjualan bulanan dan kontribusi kategori produk terhadap total pendapatan?
Produk atau kategori apa yang berkinerja buruk (underperformer) berdasarkan kuantitas penjualan dan harga?
Bagaimana kita dapat mengsegmentasi pelanggan berdasarkan perilaku pembelian mereka (Recency, Frequency, Monetary)?
Apakah ada hubungan signifikan antara anggaran iklan (Ad_Budget) dan total penjualan (Total_Sales)?
2. Data Wrangling
Beberapa langkah pembersihan dan persiapan data yang dilakukan meliputi:

Penanganan Nilai Hilang: Mengidentifikasi dan menangani nilai yang hilang pada kolom Description dan CustomerID (pada dataset df awal), serta memastikan tidak ada NaN pada kolom kunci untuk analisis seperti Total_Sales dan Ad_Budget (untuk dataset df_praktikum).
Konversi Tipe Data: Mengonversi kolom tanggal (InvoiceDate dan Order_Date) ke tipe data datetime untuk memungkinkan analisis berbasis waktu.
Pembersihan Data Numerik: Menghapus baris transaksi dengan UnitPrice kurang dari atau sama dengan nol untuk memastikan keakuratan perhitungan penjualan.
Pembuatan Fitur Baru: Menghitung Total_Sales (Quantity * UnitPrice) dan mengekstrak Month dari tanggal transaksi untuk analisis tren.
3. Insights (Wawasan)
Berikut adalah beberapa wawasan utama yang diperoleh dari analisis data:

Tren Penjualan Bulanan (dari df):
Visualisasi tren penjualan bulanan menunjukkan peningkatan penjualan yang signifikan menjelang akhir tahun, terutama pada bulan November, yang mungkin mengindikasikan musim belanja liburan atau kampanye promosi khusus. Penjualan mencapai puncaknya di November dan menurun pada Desember (data tidak lengkap).

Korelasi Antar Variabel Numerik (dari df):
Heatmap Korelasi

Heatmap korelasi menunjukkan korelasi positif yang sangat kuat antara Quantity dan Total_Sales (sekitar 0.90), yang merupakan hal yang wajar karena Total_Sales dihitung dari Quantity dan UnitPrice. Korelasi antara UnitPrice dan Total_Sales relatif lemah dan negatif (sekitar -0.18), menunjukkan bahwa produk dengan harga per unit yang lebih tinggi tidak selalu berkorelasi dengan total penjualan yang lebih tinggi.

Kategori Produk Underperformer (dari df_praktikum):
Analisis underperformer, yang mengidentifikasi kategori produk dengan Avg_Price_Per_Unit di atas rata-rata keseluruhan tetapi Total_Quantity di bawah kuartil pertama, mengidentifikasi 'Home Decor' sebagai satu-satunya kategori underperformer dalam dataset df_praktikum. Ini menunjukkan bahwa meskipun produk-produk dalam kategori ini mungkin memiliki harga rata-rata yang relatif tinggi, mereka tidak terjual dalam jumlah besar.

Kontribusi Penjualan per Kategori Produk (dari df_praktikum):
Pie Chart Kontribusi Kategori

Pie chart kontribusi penjualan menunjukkan bahwa 'Electronics' (sekitar 24.9%) dan 'Books' (sekitar 23.5%) adalah kategori dengan kontribusi terbesar terhadap total penjualan, diikuti oleh 'Fashion'. Ini menyoroti dominasi beberapa kategori dalam menghasilkan pendapatan.

Uji Hipotesis (Pengaruh Ad_Budget terhadap Total_Sales):
Uji t independen yang dilakukan untuk membandingkan Total_Sales antara kelompok dengan Ad_Budget tinggi dan rendah menunjukkan P-value sebesar 0.829. Karena P-value ini jauh lebih besar dari tingkat signifikansi umum (alpha = 0.05), kita gagal menolak hipotesis nol. Ini berarti tidak ada bukti statistik yang signifikan bahwa peningkatan Ad_Budget di atas median menghasilkan peningkatan Total_Sales yang signifikan dalam data yang tersedia.

4. Recommendation (Rekomendasi)
Berdasarkan wawasan di atas, perusahaan dapat mempertimbangkan langkah-langkah berikut:

Fokus pada Kategori Berkinerja Tinggi: Menginvestasikan lebih banyak sumber daya pada kategori Electronics dan Books yang terbukti menjadi pendorong pendapatan utama. Ini bisa berupa kampanye pemasaran yang lebih agresif atau penawaran produk yang diperluas.
Evaluasi Kategori Underperformer: Untuk 'Home Decor', perlu dilakukan investigasi lebih lanjut. Apakah harga terlalu tinggi untuk pasar target? Apakah ada masalah dengan pemasaran atau deskripsi produk? Pertimbangkan penyesuaian harga, promosi khusus, atau bahkan restrukturisasi lini produk.
Pemanfaatan Segmentasi RFM: Menggunakan segmen pelanggan dari analisis RFM untuk mengembangkan strategi pemasaran yang lebih bertarget. Misalnya, pelanggan dengan skor RFM tinggi (loyal dan sering berbelanja) dapat ditargetkan dengan program loyalitas eksklusif, sementara pelanggan dengan recency rendah mungkin memerlukan kampanye re-engagement.
Rethink Strategi Anggaran Iklan: Berdasarkan hasil uji hipotesis, investasi Ad_Budget yang lebih tinggi saat ini tidak menunjukkan dampak signifikan pada Total_Sales. Perusahaan harus mengevaluasi efektivitas kampanye iklan saat ini dan mempertimbangkan untuk mengoptimalkan alokasi anggaran, mungkin dengan berfokus pada saluran atau jenis iklan yang berbeda, atau meninjau metrik keberhasilan selain hanya Total_Sales langsung.
Analisis Musiman: Memanfaatkan pola penjualan musiman, terutama lonjakan di bulan November, untuk merencanakan stok, kampanye pemasaran, dan promosi jauh sebelumnya guna memaksimalkan pendapatan.
