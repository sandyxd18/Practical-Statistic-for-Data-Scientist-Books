# Practical Statistics for Data Scientists (Python Implementation)

Repositori ini berisi implementasi praktis konsep statistika untuk *data science* dan *machine learning* menggunakan Python. Materi dan kode pada repositori ini mengacu pada buku **"Practical Statistics for Data Scientists"** oleh Peter Bruce, Andrew Bruce, dan Peter Gedeck.

Setiap bab disusun dalam format Jupyter Notebook interaktif yang menggabungkan penjelasan konsep teoritis, penurunan matematis praktis, serta implementasi kode langsung dengan data riil.

---

## Daftar Isi dan Rincian Tiap Bab

### [Bab 1: Exploratory Data Analysis (EDA)](Bab1_Exploratory_Data_Analysis.ipynb)
Fokus pada pemahaman karakteristik data mentah sebelum pemodelan statistik atau machine learning:
- **Elements of Structured Data**: Klasifikasi tipe data (numerik kontinu, numerik diskrit, kategorikal ordinal, dan kategorikal nominal/biner).
- **Rectangular Data**: Struktur data tabular (fitur, target, dan representasi matriks).
- **Estimates of Location**: Pengukuran tendensi sentral tahan banting (*robust statistics*): Mean, Trimmed Mean, Median, serta Weighted Mean dan Weighted Median menggunakan data populasi dan tingkat kejahatan antar negara bagian AS.
- **Estimates of Variability**: Pengukuran penyebaran data: Variance, Standard Deviation, Mean Absolute Deviation (MAD), Median Absolute Deviation from Median, dan Interquartile Range (IQR).
- **Exploring Data Distribution**: Visualisasi distribusi melalui Percentile, Boxplot, Frequency Table, Histogram, dan Kernel Density Estimation (KDE).
- **Exploring Binary and Categorical Data**: Modus, Expected Value, Bar Chart, dan Pie Chart menggunakan data keterlambatan maskapai penerbangan di bandara DFW.
- **Correlation**: Analisis korelasi Pearson, scatterplot matrix, serta visualisasi heatmap korelasi pada pergerakan return saham komponen indeks S&P 500.
- **Exploring Two or More Variables**: Visualisasi relasi bivariat dan multivariat pada data besar menggunakan Hexagonal Binning dan Contour Plot (data pajak properti King County), serta Contingency Table / Cross-tabulation (data pinjaman Lending Club).

### [Bab 2: Data and Sampling Distributions](Bab2_Data_and_Sampling_Distributions.ipynb)
Membahas perbedaan krusial antara distribusi data mentah dengan distribusi sampling sebuah statistik:
- **Random Sampling dan Sample Bias**: Prinsip sampling representatif, Simple Random Sampling, dan Stratified Sampling untuk mencegah bias seleksi.
- **Selection Bias**: Bahaya *survivorship bias*, spesifikasi model spekulatif, dan *data snooping* dalam riset kuantitatif.
- **Sampling Distribution of a Statistic**: Simulasi empiris Central Limit Theorem (CLT) dan perhitungan Standard Error menggunakan data pendapatan peminjam.
- **The Bootstrap**: Metode resampling dengan pengembalian (*sampling with replacement*) untuk mengestimasi variabilitas dan distribusi statistik tanpa bergantung pada asumsi parametrik.
- **Confidence Intervals (Selang Kepercayaan)**: Perhitungan selang kepercayaan 90% dan 95% berbasis metode Bootstrap Percentile dan Bootstrap Standard Error.
- **Distribusi Probabilitas Penting**:
  - *Normal Distribution*: Standarisasi z-score dan evaluasi kenormalan melalui Q-Q Plot (*quantile-quantile plot*).
  - *Long-Tailed Distributions*: Analisis skewness, kurtosis, dan karakteristik *fat tails* pada return aset finansial (data saham Netflix).
  - *Student's t-Distribution*: Karakteristik distribusi untuk sampel kecil dan penentuan derajat bebas (*degrees of freedom*).
  - *Binomial Distribution*: Pemodelan probabilitas diskrit untuk kejadian biner (sukses/gagal) pada eksperimen multi-trial.
  - *Chi-Square Distribution*: Distribusi statistik deviasi antara frekuensi observasi dan frekuensi ekspektasi.
  - *F-Distribution*: Distribusi rasio dua varians sebagai fondasi uji ANOVA dan regresi.
  - *Poisson, Exponential, dan Weibull*: Pemodelan tingkat kedatangan kejadian per unit waktu/ruang (*arrival rates*), interval waktu antar kejadian, dan analisis keandalan sistem (*survival analysis*).

### [Bab 3: Statistical Experiments and Significance Testing](Bab3_Statistical_Experiments_and_Significance_Testing.ipynb)
Membahas metodologi pengujian hipotesis dan evaluasi signifikansi eksperimen:
- **A/B Testing**: Struktur eksperimen terkontrol dengan kelompok Treatment dan Control, penentuan metrik keberhasilan, dan randomisasi alokasi subjek.
- **Hypothesis Testing**: Formulasi Hipotesis Nol ($H_0$) dan Hipotesis Alternatif ($H_a$), serta evaluasi risiko kesalahan Type I ($\alpha$, *false positive*) dan Type II ($\beta$, *false negative*).
- **Resampling via Permutation Test**: Uji signifikansi berbasis pengacakan label kelompok secara berulang untuk menghasilkan distribusi null empiris tanpa asumsi normalitas (diuji pada data durasi sesi web).
- **Statistical Significance dan p-Values**: Interpretasi p-value sebagai probabilitas teramatinya hasil ekstrem jika $H_0$ benar, bukan ukuran besaran dampak praktis (*effect size*).
- **t-Tests**: Penerapan uji t dua sampel independen menggunakan `scipy.stats.ttest_ind`.
- **Multiple Testing**: Masalah inflasi kesalahan tipe I ketika menjalankan banyak uji sekaligus, penanganannya dengan koreksi Bonferroni dan False Discovery Rate (FDR).
- **Analysis of Variance (ANOVA)**: Pengujian kesamaan rata-rata antar lebih dari dua kelompok sekaligus dengan F-statistic dan uji permutasi multi-kelompok (data empat sesi halaman web).
- **Chi-Square Test**: Pengujian independensi dua variabel kategorikal pada tabel kontinjensi (data konversi klik web).
- **Multi-Arm Bandit Algorithm**: Implementasi algoritma Epsilon-Greedy untuk menyeimbangkan *exploration* (menguji varian baru) dan *exploitation* (memaksimalkan varian terbaik) secara adaptif dalam optimasi konversi.
- **Statistical Power and Sample Size**: Penentuan ukuran sampel minimum sebelum eksperimen dijalankan berdasarkan tingkat signifikansi ($\alpha$), *statistical power* ($1 - \beta$), dan estimasi *effect size* (Cohen's d / h).

### [Bab 4: Regression and Prediction](Bab4_Regression_and_Prediction.ipynb)
Membahas estimasi relasi antar variabel untuk prediksi dan inferensi:
- **Simple Linear Regression**: Estimasi parameter garis regresi dengan metode Ordinary Least Squares (OLS), perhitungan koefisien kemiringan (*slope*), *intercept*, dan analisis residual.
- **Multiple Linear Regression**: Pemodelan multivariat menggunakan data harga rumah King County (`house_sales.csv`), evaluasi kualitas model menggunakan metrik RMSE, R-squared ($R^2$), dan Adjusted R-squared.
- **Prediction Using Regression**: Perbedaan selang kepercayaan (Confidence Interval) untuk rata-rata ekspektasi terhadap selang prediksi (Prediction Interval) untuk observasi individual baru.
- **Factor Variables dalam Regresi**: Penanganan fitur kategorikal melalui *dummy coding* / *one-hot encoding*, penetapan kategori referensi, dan pencegahan *dummy variable trap*.
- **Interpretasi Persamaan Regresi**: Memahami makna koefisien dengan asumsi *ceteris paribus*, fenomena *confounding variables*, serta deteksi multikolinearitas menggunakan Variance Inflation Factor (VIF).
- **Regression Diagnostics**:
  - *Outliers*: Deteksi nilai pencilan ekstrem menggunakan *standardized residuals*.
  - *Influential Values*: Identifikasi data yang memiliki pengaruh disproportionate terhadap garis regresi menggunakan *hat-values* (*leverage*) dan *Cook's distance*.
  - *Heteroskedasticity, Non-Normality, and Correlated Errors*: Evaluasi pola residual vs fitted values, uji Breusch-Pagan, dan visualisasi distribusi residual dengan Q-Q Plot.
  - *Partial Residual Plots*: Memeriksa apakah hubungan antar prediktor dan target bersifat linear atau memerlukan transformasi.
- **Polynomial dan Spline Regression**: Mengakomodasi relasi non-linear melalui regresi polinomial derajat tinggi dan penggunaan *polynomial splines* (B-splines / natural cubic splines) untuk fleksibilitas kurva tanpa osilasi ekstrem di ujung rentang data.

---

## Dataset yang Digunakan

Seluruh notebook memuat dataset secara otomatis dari repositori data publik buku resmi:

- `state.csv`: Data demografi, populasi, dan murder rate negara bagian AS.
- `dfw_airline.csv`: Frekuensi dan persentase keterlambatan penerbangan di Dallas/Fort Worth.
- `sp500_data.csv.gz` & `sp500_sectors.csv`: Data harga historis saham S&P 500 per sektor industri.
- `kc_tax.csv.gz`: Data perpajakan dan taksiran nilai properti King County, Washington.
- `lc_loans.csv`: Riwayat dan status pinjaman nasabah Lending Club.
- `loans_income.csv`: Sampel data pendapatan peminjam untuk simulasi distribusi sampling.
- `web_page_data.csv`: Durasi sesi pengguna pada dua tata letak halaman web (A/B testing).
- `click_rates.csv`: Data klik dan impresi untuk uji independensi Chi-Square.
- `four_sessions.csv`: Durasi sesi web di empat variasi halaman untuk uji ANOVA.
- `airline_stats.csv`: Metrik performa keterlambatan antar maskapai penerbangan.
- `house_sales.csv`: Karakteristik fisik dan harga transaksi penjualan rumah di King County.

---

## Teknologi dan Library Python

Proyek ini dibangun menggunakan pustaka komputasi numerik dan statistik standar industri:

- **Python 3**: Bahasa pemrograman utama.
- **pandas**: Manipulasi, transformasi, dan inspeksi data tabular.
- **numpy**: Operasi matriks, vektorisasi array, dan simulasi acak.
- **scipy**: Modul `scipy.stats` untuk pengujian hipotesis, fungsi probabilitas, dan uji signifikansi.
- **statsmodels**: Modul `statsmodels.api`, `statsmodels.formula.api`, dan analisis *power/sample size*.
- **matplotlib** & **seaborn**: Visualisasi distribusi, scatterplot, korelasi, dan diagnostik residual.
- **wquantiles**: Perhitungan weighted median dan weighted percentile.
- **Jupyter Notebook**: Antarmuka interaktif eksekusi kode dan visualisasi.

---

## Cara Menjalankan Proyek

1. **Clone repositori ini**:
   ```bash
   git clone https://github.com/sandyxd18/Practical-Statistic-for-Data-Scientist-Books.git
   cd Practical-Statistic-for-Data-Scientist-Books
   ```

2. **Siapkan virtual environment (opsional tetapi disarankan)**:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # Untuk Linux/macOS
   # venv\Scripts\activate   # Untuk Windows
   ```

3. **Install dependensi yang diperlukan**:
   ```bash
   pip install pandas numpy scipy statsmodels matplotlib seaborn wquantiles jupyter
   ```

4. **Jalankan Jupyter Notebook**:
   ```bash
   jupyter notebook
   ```
   Buka berkas notebook bab yang ingin dipelajari (misalnya `Bab1_Exploratory_Data_Analysis.ipynb`). Pastikan komputer terhubung ke internet saat pertama kali menjalankan notebook agar dataset dapat diunduh langsung dari sumber repositori.
