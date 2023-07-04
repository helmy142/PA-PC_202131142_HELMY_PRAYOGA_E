
# SEGMENTASI KATA

A. Teori yang mendukung 

    - pengolahan gambar
        Pengolahan gambar adalah bidang yang berhubungan dengan pemrosesan dan analisis gambar secara digital.
         Dalam proyek ini, beberapa teknik pengolahan gambar digunakan, seperti konversi ke skala keabuan, thresholding, dan deteksi kontur.
    - Thresholding
        Thresholding adalah teknik pengolahan gambar yang digunakan untuk mengubah gambar menjadi gambar biner, 
        di mana piksel diubah menjadi nilai biner (hitam atau putih) berdasarkan nilai ambang tertentu sehingga dapat 
        menghasilkan gambar biner yang memiliki kontur teks yang jelas.
    - Deteksi Kontur
        Deteksi kontur adalah proses pengenalan pola untuk menemukan dan mengidentifikasi batas atau kontur objek dalam gambar.
    - segmentasi kata 
        digunakan untuk memisahkan kata kata dalam teks menjadi unit unit individu.

B. Tahapan cara menyelesaikan projek
    
    1. import library OpenCV yang digunakan yaiut cv2 untuk pemrosesan gambar, numpy untuk manipulasi array , dan matplotlib untuk visualiasi grafis
    2. kemudian pada cell In 2 definisikan fungsi "preprocess_image(image)" untuk melakukan pemrosesan pada gambar.
       Langkah-langkahnya termasuk mengubah gambar menjadi skala keabuan (COLOR_BGR2GRAY), menerapkan blur Gaussian (cv2.GaussianBlur),
       dan melakukan thresholding (cv2.threshold) untuk menghasilkan gambar biner.
    3. kemudian pada cell In 7 definisikan fungsi "segment_words(image)"
       Fungsi segment_words menerima gambar sebagai input dan         mengembalikan daftar kata-kata yang tersegmentasi. 
       Fungsi ini menggunakan fungsi preprocess_image untuk memperoleh gambar biner yang diolah sebelumnya. Kemudian, menggunakan cv2.findContours, 
       ia menemukan kontur pada gambar biner tersebut. Setiap kontur dicek untuk memastikan bahwa luasnya berada dalam rentang yang 
       valid (100 hingga 10000) dan jika valid,kata tersebut disimpan dalam daftar words bersama dengan informasi persegi kotaknya.
    4. pada cell 8, kita membaca gambar dari file menggunakan cv2.imread
    5. pada cell 9, kitamemanggil fungsi segment_words untuk melakukan segmentasi kata pada gambar tersebut
    6. kemudian pada cell 10, kita menggunakan perulangan for dan
       kita menggambar persegi pada setiap kata dalam gambar menggunakan cv2.rectangle
    7. dan pada cell 11, kita menampilkan gambar asli pada subplot pertama dan gambar yang telah disegmentasikan pada subplot kedua. 
       kemudian  subplots(1, 2, figsize=(15, 11)) menentukan bahwa akan ada satu baris dan dua kolom subplot,
       dengan ukuran keseluruhan jendela gambar sebesar 15x11 inci. Selanjutnya, variabel ax digunakan untuk mengakses setiap subplot.
       Pada subplot pertama (ax[0]), gambar asli ditampilkan menggunakan imshow(). Argumen image adalah gambar yang ingin ditampilkan, 
       dan cmap="gray" mengatur tampilan gambar dalam skala abu-abu. set_title() digunakan untuk memberikan judul pada subplot tersebut,
       yaitu "Original Image". Pada subplot kedua (ax[1]), gambar yang telah disegmentasikan ditampilkan menggunakan imshow(). 
       Argumen segmented_image adalah gambar yang telah disegmentasikan, dan cmap="gray" mengatur tampilan gambar dalam skala abu-abu. 
       set_title() digunakan untuk memberikan judul pada subplot tersebut, yaitu "Segmented Image".

C. Jurnal Terkait

    1. "Text Segmentation from Natural Scenes" oleh A. Shahab, S. K. Shah, dan F. Shafait

