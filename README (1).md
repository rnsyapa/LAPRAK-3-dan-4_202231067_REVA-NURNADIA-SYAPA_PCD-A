
# Deteksi Tepi dan Garis, Ekstraksi Fitur

**Deteksi Tepi dan Garis**

**Deteksi Tepi (Edge Detection)**
1. Pengertian Tepi
Tepi dalam sebuah citra adalah tempat terjadinya perubahan mendadak dalam intensitas piksel. Deteksi tepi bertujuan untuk menemukan perubahan tersebut, yang sering kali menunjukkan batas objek dalam gambar. Tepi sangat penting dalam pengenalan bentuk, segmentasi citra, dan pengenalan objek.

2. Metode Deteksi Tepi
- Operator Sobel:
Menggunakan dua kernel (filter) konvolusi untuk menghitung perubahan intensitas dalam arah horizontal (x) dan vertikal (y).
Kernel Sobel untuk arah horizontal dan vertikal membantu dalam mendeteksi tepi dalam dua arah tersebut.
Hasil deteksi tepi biasanya merupakan kombinasi dari kedua arah ini.

- Operator Prewitt:
Mirip dengan Sobel tetapi dengan kernel yang sedikit berbeda.
Juga digunakan untuk mendeteksi tepi dalam arah horizontal dan vertikal.

- Operator Laplacian:
Menggunakan pendekatan kedua turunan (second derivative) untuk mendeteksi tepi.
Lebih sensitif terhadap noise, sehingga sering kali perlu dilakukan penghalusan citra sebelum menggunakan operator ini.

- Operator Canny:
Metode deteksi tepi yang lebih kompleks dan canggih.
Melibatkan beberapa tahapan:
- Penghalusan (Smoothing): Menggunakan filter Gaussian untuk mengurangi noise.
- Perhitungan Gradien: Menggunakan operator Sobel atau operator lainnya untuk menemukan intensitas gradien dalam arah x dan y.
- Non-maximum Suppression: Menyaring piksel yang bukan merupakan bagian dari tepi sebenarnya dengan cara menekan nilai yang bukan maksimum lokal.
- Thresholding Ganda (Double Thresholding): Menerapkan dua ambang batas untuk memisahkan piksel tepi yang kuat dan lemah.
- Pelacakan Tepi dengan Histeresis: Menghubungkan tepi lemah yang terhubung ke tepi kuat untuk menghasilkan garis tepi yang kontinu.

**Deteksi Garis (Line Detection)**

1. Pengertian Garis
Garis dalam sebuah citra adalah kumpulan piksel yang terhubung dan membentuk bentuk linear. Deteksi garis bertujuan untuk menemukan garis lurus dalam gambar, yang sering kali penting dalam pengenalan pola, pemetaan, dan analisis citra.

2. Metode Deteksi Garis
Transformasi Hough:

Teknik yang digunakan untuk mendeteksi bentuk geometris tertentu dalam citra, termasuk garis lurus.
Prinsip dasarnya adalah memetakan titik-titik dalam citra ke ruang parameter, di mana garis dalam citra menjadi titik dalam ruang parameter.

Transformasi Hough memiliki dua varian utama:
1. Transformasi Hough Standar: Mendeteksi garis lurus dengan representasi parametrik .
2. Transformasi Hough Probabilistik: Versi yang lebih efisien dari Transformasi Hough Standar, yang hanya mempertimbangkan subset piksel dalam citra.

**Aplikasi Praktis**
- Pengenalan Objek: Deteksi tepi dan garis membantu dalam mengenali dan melacak objek dalam gambar atau video.
- Segmentasi Citra: Membagi citra menjadi beberapa bagian yang lebih mudah dianalisis dengan menggunakan informasi tepi dan garis.
- Analisis Citra Medis: Membantu dalam mendeteksi struktur anatomi atau abnormalitas dalam gambar medis seperti MRI atau CT scan.
- Pengenalan Teks dan Plat Nomor: Deteksi tepi dan garis digunakan dalam sistem OCR (Optical Character Recognition) dan ANPR (Automatic Number Plate Recognition).

**Ekstraksi Fitur**

Ekstraksi fitur adalah proses dalam pengolahan citra yang bertujuan untuk mengidentifikasi dan mengambil informasi penting dari citra yang dapat digunakan untuk analisis lebih lanjut, seperti pengenalan objek, klasifikasi, atau segmentasi. Fitur-fitur ini bisa berupa tepi, tekstur, bentuk, atau pola tertentu dalam citra. 

1. Pengertian Fitur
Fitur dalam konteks pengolahan citra adalah representasi data yang mengandung informasi penting dari citra yang dapat digunakan untuk tujuan analisis lebih lanjut. Fitur ini bisa bersifat:

- Lokal: Mengambil informasi dari bagian kecil citra (misalnya, tepi atau sudut).
- Global: Mengambil informasi dari seluruh citra (misalnya, histogram warna atau frekuensi tekstur).
2. Jenis-Jenis Fitur
a. Fitur Geometri (Geometric Features)
- Tepi (Edges): Batas antara dua wilayah dengan intensitas yang berbeda. Tepi digunakan untuk mendeteksi bentuk dan struktur objek dalam citra.
- Sudut (Corners): Titik-titik di mana terdapat perubahan arah yang tajam dalam citra. Sudut sering digunakan untuk pelacakan fitur dan pengenalan objek.
- Bentuk (Shapes): Deskripsi bentuk geometris objek dalam citra. Bentuk bisa diwakili oleh kontur atau representasi parametrik.
b. Fitur Tekstur (Texture Features)
- Histogram Intensitas: Distribusi intensitas piksel dalam citra. Histogram intensitas memberikan informasi tentang variasi intensitas dalam citra.
- GLCM (Gray-Level Co-occurrence Matrix): Matriks yang mengukur frekuensi pasangan piksel dengan nilai intensitas tertentu yang muncul pada jarak dan arah tertentu. Fitur yang diekstrak dari GLCM meliputi kontras, energi, homogenitas, dan korelasi.
- LBP (Local Binary Patterns): Teknik yang digunakan untuk mendeskripsikan tekstur lokal dalam citra dengan mengkodekan hubungan antara piksel pusat dan piksel tetangga.
c. Fitur Frekuensi (Frequency Features)
- Transformasi Fourier: Mengubah citra dari domain spasial ke domain frekuensi. Fitur frekuensi dapat memberikan informasi tentang komponen periodik dalam citra.
- Transformasi Wavelet: Teknik yang menguraikan citra menjadi komponen frekuensi berbeda dengan resolusi spasial yang berbeda. Transformasi wavelet sering digunakan untuk analisis multi-resolusi.
3. Metode Ekstraksi Fitur
a. Deteksi Tepi
- Operator Sobel: Menggunakan filter konvolusi untuk mendeteksi tepi horizontal dan vertikal.
- Operator Canny: Metode deteksi tepi yang lebih canggih yang melibatkan penghalusan, perhitungan gradien, dan thresholding ganda.
b. Deteksi Sudut
- Operator Harris: Teknik deteksi sudut yang menggunakan matriks gradien untuk menemukan titik sudut dalam citra.
- FAST (Features from Accelerated Segment Test): Algoritma deteksi sudut yang cepat dan efisien, sering digunakan dalam aplikasi real-time.
c. Deskriptor Bentuk
- Kontur: Representasi bentuk objek dalam citra dengan mengikuti batas objek.
- Deskriptor Fourier: Menggunakan koefisien Fourier untuk merepresentasikan kontur objek dalam domain frekuensi.
d. Ekstraksi Tekstur
- Histogram Intensitas: Menganalisis distribusi intensitas piksel dalam citra.
- GLCM (Gray-Level Co-occurrence Matrix): Mengukur frekuensi pasangan piksel dengan nilai intensitas tertentu yang muncul pada jarak dan arah tertentu.
- LBP (Local Binary Patterns): Mengkodekan hubungan antara piksel pusat dan piksel tetangga untuk mendeskripsikan tekstur lokal.
e. Transformasi Frekuensi
- Transformasi Fourier: Mengubah citra dari domain spasial ke domain frekuensi untuk menganalisis komponen frekuensi dalam citra.
- Transformasi Wavelet: Menguraikan citra menjadi komponen frekuensi berbeda dengan resolusi spasial yang berbeda untuk analisis multi-resolusi.
4. Aplikasi Ekstraksi Fitur
- Pengenalan Objek: Mengidentifikasi dan mengklasifikasikan objek dalam citra berdasarkan fitur yang diekstraksi.
- Segmentasi Citra: Membagi citra menjadi bagian-bagian yang lebih homogen berdasarkan fitur yang diekstraksi.
- Pengenalan Wajah: Mengidentifikasi wajah dalam citra dengan menggunakan fitur seperti tepi, sudut, dan tekstur.
- Analisis Citra Medis: Mendeteksi dan mengklasifikasikan struktur anatomi atau abnormalitas dalam gambar medis seperti MRI atau CT scan.
