# Struktur Sistem Operasi

## - Struktur Sederhana / Sistem Monolitik
Struktur Sederhana / Sistem Monolitik merupakan struktur sistem operasi sederhana yang dilengkapi dengan operasi “dual” pelayanan {sistem call} yang diberikan oleh sistem operasi.Semua komponen sistem operasi bercampur
Semua rutin sistem operasi dapat mengakses rutin yang lainnya,Tidak ada pemisahan yang jelas antara aplikasi dan sistem
operasi, Akibatnya program-program malware mudah memodifikasi dan merusak sistem operasi, Program aplikasi memiliki akses untuk memodifikasi bagian sistem operasi
Contoh : Ms-Dos, UNIX

Mekanisme dan prinsip kerja model struktur monolitik sistem operasi ini adalah sebagai berikut:

1. User program melakukan “trap” pada karnel

2. Intruksi berpindah dari user mode ke monitor

mode dan mentransfer control ke sistem operasi.

3. Sistem operasi mengecek parameter — parameter dari pemanggilan tersebut, untuk menentukan sistem call mana yang memanggil.

4. Sistem operasi menunjuk ke suatu table yang berisi slot ke-k yang menunjuk sistem call K (Kontrol).

5. Kontrol akan dikembalikan kepada user program, jika sistem call telah selesai mengerjakan tugasnya.

#### Keunggulan Sistem Sederhana / Monolitik
1) Layanan dapat dilakukan sangat cepat karena terdapat di satu ruang alamat.

#### Kelemahan Sistem Sederhana / Monolitik
1)  Pengujian dan penghilangan kesalahan sulit karena tidak dapat dipisahkan dan dilokalisasi.

2) Sulit dalam menyediakan fasilitas pengamanan. Kurang efisien dalam penggunaan memori dimana setiap computer harus menjalankan kernel yang besar sementara tidak memerlukan seluruh layanan yang disediakan kernel.

3) Kesalahan pemrograman satu bagian dari kernel menyrbabakan matinya seluruh sistem.

## - Pendekatan Berlapis
Sistem operasi dibentuk secara hirarki berdasar lapisan — lapisan (layered), dimana lapisan-lapisan bawa memberi layanan lapisan lebih atas. Lapisan yang paling bawah adalah perangkat keras dan yang paling tinggi adalah user- interface atau programaplikasi. Sebuah lapisan adalah implementasi dari obyek abstrak yang merupakan enkapsulasi dari data dan operasi yang bisa memanipulasi data tersebut. programaplikasi. Rutin-rutin pada suatu lapisan hanya boleh menggunkan rutinrutin lapisan di bawahnya Contoh : THE System

#### Kelebihan Sistem Berlapis
1) Mempermudah debug dan verifikasi sistem, Lapisan pertama bisa didebug tanpa mengganggu sistem yang lain.

2) Pendekatan berlapis menyederhanakan rancangan, spesifikasi dan implementasi sistem operasi.

#### Kelemahan Sistem Berlapis
1) Fungsi-fungsi sistem operasi diberikan ke tiap lapisan secara hati-hati.

2) Hanya bisamenggunakan lapisan dibawahnya, Tidak efisien dibandingkan tipe yang lain.

## - Kernel Mikro
Metode struktur ini adalah menghilangkan komponen-komponen yang tidak diperlukan dari kernel dan mengimplementasikannya sebagai sistem dan program-program level user. Hal ini akan menghasilkan kernel yang kecil. Menyusun sistem operasi dengan menghapus semua komponen yang tidak esensial dari kernel, dan mengimplementasikannya sebagai sistemprogram dan level pengguna.

Fungsiutama: mendukung fasilitas komunikasi antara program klien dan bermacam-macam layanan yang juga berjalan diuser-space

Sistem operasi yang menggunakan micro kernel umumnya secara dramatis memiliki kinerja di bawah kinerja sistem operasi yang menggunakan monolithic kernel. Hal ini disebabkan oleh adanya overhead yang terjadi akibat proses input/output dalam kernel yang ditujukan untuk mengganti konteks (context switch) untuk memindahkan data antara aplikasi dan server.

Contoh Sistem operasi yang menggunakan struktur ini adalah : TRU64 UNIX, MacOSX dan QNX.

#### Kelebihan Kernel Mikro
1) ketika layanan baru akan ditambahkan ke userspace, kernel tidak perlu dimodif

2) OS lebih mudah ditempatkan pada suatu desain perangkat keras ke desain lainnya

3) Kode yang kecil dan lebih aman,mendukung keamanan reliabilitas lebih.

#### Kekurangan Kernel Mikro
1) kinerja akan berkurang selagi bertambahnya fungsi- fungsi yang digunakan.
