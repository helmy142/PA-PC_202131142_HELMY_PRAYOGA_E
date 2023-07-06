# SEGMENTASI KATA
Terdapat beberapa teori dalam pengolahan citra yang mendukung source code deteksi segmentasi kata tersebut. Berikut adalah penjelasan teori-teori tersebut:
1. **Konversi ke Citra Skala Abu-abu**: Konversi gambar ke citra skala abu-abu merupakan langkah awal yang umum dilakukan dalam pengolahan citra. Dalam citra skala abu-abu, setiap piksel memiliki intensitas keabuan tunggal yang mencerminkan tingkat kecerahan. Konversi ini membantu dalam mengurangi kompleksitas gambar dan mempertahankan informasi yang relevan untuk deteksi objek.

2. **Gaussian Blur**: Gaussian blur adalah suatu teknik dalam pengolahan citra untuk mengurangi noise dan menghaluskan gambar. Metode ini menerapkan filter Gaussian pada gambar untuk mengaburkan piksel-piksel sehingga mengurangi perbedaan intensitas yang tajam dan menjadikan transisi antara objek lebih halus. Hal ini membantu memperbaiki kualitas gambar dan meningkatkan efektivitas thresholding.

3. **Thresholding**: Thresholding adalah metode yang umum digunakan dalam segmentasi objek pada gambar. Dengan thresholding, nilai piksel diubah menjadi dua kategori berdasarkan ambang tertentu: piksel di atas ambang akan dianggap sebagai bagian objek dan piksel di bawah ambang akan dianggap sebagai bagian latar belakang. Dalam deteksi segmentasi kata, thresholding digunakan untuk mengubah gambar menjadi gambar biner, di mana kata-kata ditandai sebagai piksel bernilai putih dan latar belakang sebagai piksel bernilai hitam.

4. **Pencarian Kontur**: Pencarian kontur adalah teknik untuk mengidentifikasi garis yang melingkupi objek atau kata pada gambar. Kontur dapat ditemukan menggunakan berbagai algoritma, seperti algoritma Canny atau algoritma pencarian kontur dalam OpenCV. Pencarian kontur membantu dalam mengidentifikasi area yang berbeda dalam gambar, termasuk kata-kata.

5. **Bounding Rectangle**: Bounding rectangle atau persegi kotak mengelilingi kontur atau objek yang terdeteksi. Dalam deteksi segmentasi kata, bounding rectangle digunakan untuk menandai batas-batas setiap kata yang tersegmentasi. Informasi koordinat persegi kotak ini digunakan untuk memotong bagian gambar yang sesuai dengan setiap kata dan menampilkan persegi kotak pada gambar asli.


Tahapan cara menyelesaikan projek

1. import library OpenCV yang digunakan yaiut cv2 untuk pemrosesan gambar, numpy untuk manipulasi array , dan matplotlib untuk visualiasi grafis.
2. kemudian pada cell In 2 definisikan fungsi "preprocess_image(image)" untuk melakukan pemrosesan pada gambar.
   Langkah-langkahnya termasuk mengubah gambar menjadi skala keabuan (COLOR_BGR2GRAY), menerapkan blur Gaussian (cv2.GaussianBlur), dan melakukan thresholding 
   (cv2.threshold) untuk menghasilkan gambar biner.
3. kemudian pada cell In 7 definisikan fungsi "segment_words(image)" Fungsi segment_words menerima gambar sebagai input dan mengembalikan daftar kata-kata 
   yang tersegmentasi.Fungsi ini menggunakan fungsi preprocess_image untuk memperoleh gambar biner yang diolah sebelumnya. Kemudian, menggunakan cv2.findContours, 
   ia menemukan kontur pada gambar biner tersebut. Setiap kontur dicek untuk memastikan bahwa luasnya berada dalam rentang yang 
   valid (100 hingga 10000) dan jika valid,kata tersebut disimpan dalam daftar words bersama dengan informasi persegi kotaknya.
4. pada cell 8, kita membaca gambar dari file menggunakan cv2.imread
5. pada cell 9, kitamemanggil fungsi segment_words untuk melakukan segmentasi kata pada gambar tersebut
6. kemudian pada cell 10, kita menggunakan perulangan for dan kita menggambar persegi pada setiap kata dalam gambar menggunakan cv2.rectangle
7. dan pada cell 11, kita menampilkan gambar asli pada subplot pertama dan gambar yang telah disegmentasikan pada subplot kedua. kemudian  subplots(1, 2, figsize= 
   (15, 11)) menentukan bahwa akan ada satu baris dan dua kolom subplot,dengan ukuran keseluruhan jendela gambar sebesar 15x11 inci. Selanjutnya, variabel ax 
    digunakan untuk mengakses setiap subplot. Pada subplot pertama (ax[0]), gambar asli ditampilkan menggunakan imshow(). Argumen image adalah gambar yang ingin ditampilkan,  dan cmap="gray" mengatur tampilan gambar dalam skala abu-abu. set_title() digunakan untuk memberikan judul pada subplot tersebut, yaitu "Original Image". Pada subplot kedua (ax[1]), gambar yang telah disegmentasikan ditampilkan menggunakan imshow(). Argumen segmented_image adalah gambar yang telah disegmentasikan, dan cmap="gray" mengatur tampilan gambar dalam skala abu-abu. set_title() digunakan untuk memberikan judul pada subplot tersebut, yaitu "Segmented Image".


Jurnal Terkait

"Word Segmentation Method for Handwritten Documents based on Structured Learning" https://ieeexplore.ieee.org/document/7004865/

