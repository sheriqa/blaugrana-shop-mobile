1. Dalam Flutter, widget tree adalah struktur hierarki yang menggambarkan bagaimana seluruh elemen tampilan aplikasi tersusun dari widget-widget kecil. Setiap bagian antarmuka, seperti teks, tombol, gambar, maupun tata letak, semuanya merupakan widget yang saling bertumpuk membentuk sebuah pohon. Di dalam pohon ini, setiap widget bisa menjadi parent (induk) yang membungkus satu atau lebih child (anak) widget. Hubungan parent–child menentukan bagaimana tampilan dan perilaku antarelemen diatur: parent bertanggung jawab terhadap posisi, ukuran, serta tata letak child-nya, sementara child mengikuti konteks yang diberikan oleh parent, seperti tema atau arah teks. Meskipun demikian, child tidak dapat secara langsung memengaruhi parent; komunikasi ke arah atas biasanya dilakukan melalui callback atau mekanisme state management. Struktur ini membuat Flutter efisien dan fleksibel dalam membangun antarmuka pengguna yang reaktif dan terorganisir.
2. a. MaterialApp
        Widget utama yang menjadi root aplikasi Flutter berbasis Material Design. Ia menyediakan struktur dan tema dasar aplikasi, seperti warna, font, dan navigasi.
    b. Scaffold
        Menyediakan kerangka dasar tampilan layar yang terdiri dari area appBar, body, floatingActionButton, drawer, dsb yang digunakan untuk menampung keseluruhan isi halaman
    c. AppBar
        Bagian atas halaman (biasanya berupa bar) yang menampilkan judul aplikasi atau tombol navigasi. Dalam kode ini, AppBar digunakan untuk menampilkan teks “Blaugrana Shop"
    d. Text
        Menampilkan teks di layar. Contohnya digunakan untuk menampilkan judul, nama, NPM, kelas, dan label pada tombol-tombol.
    e. TextStyle
        Memberikan gaya pada teks seperti warna, ukuran huruf, dan ketebalan (fontWeight).
    f. Padding
        Memberikan jarak di sekeliling widget anaknya. Misalnya, pada Padding(all: 16.0) di sekitar Column agar konten tidak menempel ke tepi layar.
    g. Column
        Widget layout yang menyusun anak-anaknya secara vertikal dari atas ke bawah. Di sini digunakan untuk menata Row, SizedBox, Center, dan GridView.count.
    h. Row
        Widget layout yang menyusun anak-anaknya secara horizontal dari kiri ke kanan. Di proyek ini digunakan untuk menampilkan tiga InfoCard sejajar.
    i. SizedBox
        Berfungsi memberikan ruang kosong dengan ukuran tertentu. Misalnya SizedBox(height: 16.0) memberi jarak vertikal antara elemen.
    j. Center
        Menempatkan widget anaknya di posisi tengah secara horizontal dan vertikal dalam ruang yang tersedia.
    k. GridView.count
        Widget layout berbentuk grid dengan jumlah kolom tertentu (crossAxisCount). Dalam proyek ini digunakan untuk menampilkan daftar ItemCard dalam bentuk 3 kolom.
    l. Card
        Menampilkan tampilan bergaya kartu dengan bayangan (elevation). Digunakan di dalam InfoCard untuk menampilkan data NPM, nama, dan kelas dengan tampilan rapi.
    m. Container
        Widget serbaguna yang dapat berisi elemen layout, padding, ukuran, warna latar, dan sebagainya. Di sini Container digunakan di dalam Card dan ItemCard untuk mengatur ukuran dan jarak isi.
    n. MediaQuery
        Memberikan informasi tentang ukuran layar perangkat. Di InfoCard, digunakan agar lebar kartu menyesuaikan ukuran layar (MediaQuery.of(context).size.width / 3.5).
    o. Material
        Menyediakan efek visual Material Design seperti warna dasar dan efek gelombang (ripple). Digunakan di ItemCard agar InkWell bisa menampilkan efek sentuhan.
    p. InkWell
        Memberikan respon interaktif ketika pengguna menekan widget-nya. Dalam kode ini, InkWell menampilkan SnackBar saat kartu ditekan.
    q. SnackBar
        Pesan singkat yang muncul di bagian bawah layar untuk memberi umpan balik kepada pengguna. Misalnya menampilkan “Kamu telah menekan tombol All Products!”.
    r. ScaffoldMessenger
        Digunakan untuk menampilkan atau menyembunyikan SnackBar di dalam Scaffold. Dipanggil ketika pengguna menekan ItemCard.
    s. Icon
        Menampilkan ikon dari pustaka Icons. Dalam proyek ini, ikon digunakan untuk menggambarkan fungsi dari setiap menu (storefront, inventory_2, add_box).
    t. EdgeInsets
        Menentukan nilai padding atau margin (jarak dalam/luar). Misalnya EdgeInsets.all(16.0) memberi jarak sama di semua sisi.
    u. Column (di dalam InfoCard dan ItemCard)
        Menyusun teks dan ikon di dalam kartu secara vertikal agar tampil rapi di tengah.
3. Widget MaterialApp berfungsi sebagai kerangka utama aplikasi Flutter yang menggunakan gaya desain Material Design dari Google. Widget ini menyediakan pengaturan dasar seperti tema, warna, navigasi antarhalaman, serta struktur tampilan utama aplikasi. MaterialApp sering digunakan sebagai widget root karena ia menjadi pembungkus seluruh widget lain dan menyediakan konteks Material Design yang diperlukan agar komponen seperti Scaffold, AppBar, dan SnackBar dapat berfungsi dengan benar. Tanpa MaterialApp, aplikasi tidak akan memiliki sistem navigasi, tema, atau tampilan khas Material Design yang konsisten di seluruh layar.
4. Perbedaan antara StatelessWidget dan StatefulWidget terletak pada kemampuannya dalam mengelola perubahan tampilan. StatelessWidget merupakan widget yang tidak memiliki keadaan (state), sehingga tampilannya bersifat tetap dan hanya bergantung pada data yang diberikan saat pembuatan. Contohnya adalah teks, ikon, atau tombol yang tidak berubah selama aplikasi berjalan. Sebaliknya, StatefulWidget memiliki state yang dapat berubah seiring waktu, memungkinkan tampilan diperbarui ketika terjadi interaksi pengguna atau perubahan data, seperti pada form input, animasi, atau penghitung (counter). StatelessWidget digunakan ketika tampilan bersifat statis, sedangkan StatefulWidget dipilih ketika tampilan perlu bereaksi terhadap perubahan data atau aksi pengguna secara dinamis.
5. BuildContext adalah objek yang merepresentasikan posisi suatu widget di dalam widget tree Flutter. Objek ini memberikan akses ke informasi tentang lingkungan tempat widget tersebut berada, seperti tema, ukuran layar, navigasi, serta hubungan dengan widget lain di atasnya (parent). BuildContext penting karena menjadi penghubung antara widget dan struktur hierarki aplikasi Flutter — melalui konteks inilah widget dapat berinteraksi dengan elemen lain, misalnya memanggil Theme.of(context) untuk mengambil warna tema, Navigator.of(context) untuk berpindah halaman, atau ScaffoldMessenger.of(context) untuk menampilkan SnackBar. Dalam metode build(), parameter context digunakan agar widget dapat membangun tampilan sesuai dengan posisi dan kondisi tempatnya berada di widget tree, sehingga setiap widget dapat mengetahui lingkungannya dan berfungsi dengan benar dalam keseluruhan struktur aplikasi.
6. Dalam Flutter, hot reload adalah fitur yang memungkinkan pengembang melihat hasil perubahan kode secara langsung tanpa perlu menjalankan ulang aplikasi dari awal. Saat hot reload dijalankan, Flutter hanya memuat ulang bagian kode yang mengalami perubahan ke dalam Dart Virtual Machine dan memperbarui tampilan UI tanpa menghapus state aplikasi yang sedang berjalan. Misalnya, ketika warna tombol atau teks diubah, hasilnya langsung terlihat tanpa kehilangan data atau posisi halaman yang sedang aktif. Sementara itu, hot restart menjalankan ulang seluruh aplikasi dari awal dan menghapus semua state yang ada, meskipun prosesnya tetap lebih cepat dibandingkan full restart. Dengan demikian, hot reload lebih cocok digunakan untuk perubahan kecil pada tampilan atau logika, sedangkan hot restart digunakan ketika perubahan memengaruhi inisialisasi awal aplikasi.