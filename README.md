# Amazon Sales Data Preparation & Profitability Analysis

## Ringkasan
Melakukan eksplorasi data mendalam, *data cleaning*, analisis statistik, hingga visualisasi tren penjualan pada dataset transaksi e-commerce Amazon. Proyek ini bertujuan untuk mengidentifikasi anomali data, memetakan kategori produk yang paling menguntungkan versus yang merugikan, serta memberikan rekomendasi strategi penetapan harga dan pengelolaan stok.

## Problem Statement
Menganalisis data transaksi ritel memerlukan ketelitian tinggi karena sering kali menyimpan permasalahan tersembunyi seperti *outlier*, inkonsistensi, atau anomali pada nilai penjualan (*Sales*), jumlah (*Quantity*), dan keuntungan (*Profit*). Tanpa pembersihan dan analisis mendalam, produk yang tampak laris justru bisa mendatangkan kerugian bagi perusahaan.

## Data Exploration
- **Sumber Data:** Dataset Transaksi Amazon (`data_marketing_growth_analytics.csv` / Amazon Sales Dataset)
- **Ukuran Dataset:** 3.203 baris × 10 kolom
- **Periode Waktu:** 2011 – 2014
- **Tipe Data:** 5 String/Categorical, 2 Datetime, 2 Float, 1 Integer
- **Kolom Utama:** `Order ID`, `Order Date`, `Ship Date`, `EmailID`, `Geography`, `Category`, `Product Name`, `Sales`, `Quantity`, `Profit`
- **Statistik Deskriptif:** 
  - Rata-rata (*Mean*): Sales = $226.49, Quantity = 3.82, Profit = $33.84
  - Median: Sales = $60.84, Quantity = 3, Profit = $11.16

## Data Preparation & Cleaning
- **Missing Value:** 0 (Tidak ada nilai kosong / *missing value*)
- **Duplikasi:** 0 (0.00% data terduplikasi)
- **Konsistensi Format:** Berhasil mengonversi kolom tanggal ke format *Datetime*; tidak ditemukan data *typo* pada kolom kategori, *Order ID*, maupun wilayah (*Geography*).
- **Analisis Outlier (Z-Score > 2):**
  - **Sales:** Terdapat 106 outlier (3.31%), dengan kategori *Tables* memiliki jumlah outlier tertinggi (20 item).
  - **Quantity:** Terdapat 145 outlier (4.53%), didominasi oleh kategori *Binders* (23 item).
  - **Profit:** Terdapat 59 outlier (1.84%), di mana *Copiers* menyumbang outlier terbanyak (13 item) serta ditemukannya anomali ekstrem seperti *Bookcases* yang merugi signifikan.

## Visualization Output & Temuan
- **Heatmap Korelasi:** Menunjukkan korelasi sempurna (1.00) antara `Order Date` dan `Ship Date` karena proses pengiriman sangat bergantung pada tanggal pemesanan. Korelasi `Sales` dan `Quantity` tercatat positif lemah (0.21).
- **Profit per Category:** Kategori **Copiers** mencatatkan total profit tertinggi ($19.327.24), sementara **Bookcases** menjadi "lubang kebocoran" terbesar dengan kerugian mencapai -$1.646,51.
- **Quantity vs Profit (Scatter Plot):** Menemukan anomali penting di mana pembelian dengan *Quantity* 5 memicu kerugian besar (hingga -$3.000 lebih), sementara *Quantity* 4 mencatatkan profit luar biasa tinggi (di atas +$6.500).
- **Profit per Order Year:** Terjadi lonjakan kurva yang sangat curam dari tahun 2013 ke 2014, di mana rata-rata profit per pesanan melonjak naik dari 30 menjadi 40.
- **Top 5 Category (Pie Chart):** Didominasi oleh **Binders** (26.6%), **Paper** (25.5%), **Furnishings** (17.2%), **Phones** (15.7%), dan **Storage** (15.0%).

## Conclusion
- Terdapat produk yang penjualannya tinggi dan laris di pasaran, namun justru merugikan perusahaan akibat struktur harga atau biaya yang tidak terkontrol dengan baik.
- Anomali pada tingkat kuantitas tertentu menunjukkan adanya ketidakefisienan diskon atau biaya operasional tersembunyi yang perlu segera dievaluasi.

## Recommendation
- Melakukan pemantauan dan audit rutin secara ketat terhadap *Sales*, *Quantity*, dan *Profit* pada produk-produk yang memiliki volume tinggi tetapi merugikan.
- Memanfaatkan kategori produk dengan frekuensi pembelian tinggi dan stabil (seperti *Paper* dan *Binders*) sebagai "pintu masuk" atau *bundling* untuk memasarkan produk bermargin tinggi (seperti *Copiers* dan *Accessories*).
- Memastikan ketersediaan stok (*inventory*) untuk kategori bervolume tinggi selalu aman demi menjaga kelangsungan arus kas dan kepuasan pelanggan.

## Tools yang Digunakan
Python (Pandas, NumPy, Seaborn, Matplotlib, Z-Score) · Excel · Heatmap · Scatter Plot · Pie Chart · Data Cleaning & Exploratory Data Analysis (EDA)

---
*Bagian dari Portofolio Graphic Design & Data Analytics Career Accelerator — Tempat Belajar (2026)*  
*Disusun oleh: Raka Dewa Dipa Mahesa Arsandy*
