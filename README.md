# CRUD-PDO
Pada Tutorial PHP CRUD PDO OOP PHP sebelumnya sudah dibahas mengenai contoh operasi create, read, update dan delete dengan gaya oop pdo. Selanjutnya pada bagian kedua ini saya akan memberikan contoh bagaimana meringkas kode query supaya bersifat universal.
Meringkas kode yang dimaksud disini adalah menyederhanakan kode supaya lebih mudah digunakan atau bersifat universal, maksudnya bersifat universal adalah misal ketika akan melakukan query pada sebuah tabel , maka kita tidak perlu membuat fungsi untuk query pertabelnya, cukup menggunakan satu perintah yang sudah diringkas.
Contohnya ketika ada ingin menampilkan pada tabel A, maka anda perlu membuat SELECT FROM A dan tabel SELECT FROM B, sedangankan jika diringkas, maka Anda tidak menulis – nulis ulang kode query. Dengan konsep OOP tentunya ini cukup mudah untuk dibuat.
| Copyleft : ROOT93
	| Terima kasih sudah membaca dan memahami kode saya. Semua contoh kode dan konsep
	| yang saya tulis bisa Anda pergunakan kembali atau memodifikasinya sesuai dengan
	| kebutuhan.
	| Terima Kasih :)
	| Author=>Ahmad Zaelani
	| ------------------------------------------------------------------------------------------
	| Catatan :
	| Anda bisa melihat tutorial sebelumnya di root93 tentang CRUD OOP PDO PHP
	| ------------------------------------------------------------------------------------------
	| link
	| parameter yang disederhanakan untuk koneksi ke database
	| ------------------------------------------------------------------------------------------
	| selectTable
	| Perintah ini digunakan untuk memilih table, atau meng-GET table berdasarkan nama table
	| dan parameter WHERE. Untuk menggunakannya Anda perlu mendefinisikannnya seperti berikut
	| Tanpa WHERE bisa diakses misal seperti :
	| $obj->selectTable('nama_table',NULLL)
	| Jika misal dengan where diakses pada fungsi lain, maka Anda bisa mendefinisikan
	| parameternya misal seperti :
	| $this->selectTable('nama_table','parameter_data=:parameter_data')
	| dan tentunya cara penggunaanya bisa Anda improvisasi sendiri sesuai konsep PDO OOP PHP 
	| ------------------------------------------------------------------------------------------
	| insertTable
	| Fungsi ini digunakan untuk menggantikan fungsi insertData() sehingga dengan cukup dengan
	| satu fungsi ini bisa beroperasi untuk input data ke berbagai macam tabel tanpa
	| harus membuat fungsi insert dan mendefinisikan ulang didalam query.
	| Untuk menggunakan perintah, Anda bisa mendefinisikan 4 parameter didalam fungsinya
	| yaitu $table, $vartable, $value, dan $array
	| $table untuk mewakili nama table
	| $vartable untuk mendefinisikan kolom tabel
	| $value untuk mendefinisikan nilai kolom tabel
	| $array untuk mendefinisikan eksekusi pada kolom tabel bersama nilainya
	| ------------------------------------------------------------------------------------------
	| getTable
	| Perintah ini bisa digunakan untuk mendapatkan data dari table 
	| dengan memnafatkan perintah selectTable(). Perintah ini menggantikan perintah 
	| sebelumnya detailData() dan detailData_duatest().
	| Pada saat MENCETAK OBJEK, Anda harus mendefinisikan data dengan get $data,
	| $par mendefinisikan kolom table untuk parameter bindParam atau execute dengan array
	| $table untuk mendefinisikan nama table dan $where untuk spesifikasi datanya
	| ------------------------------------------------------------------------------------------
	| deleteData
	| Fungsi ini menggantikan fungsi delete sebelumnya, dengan fungsi ini kita bisa ber
	| operasi untuk mendelete data dari berbagai tabel menggunakan satu fungsi ini
	| ------------------------------------------------------------------------------------------
	| pagination
	| Fungsi ini untuk penyederhanaan pagination halaman/pembagian halaman, terdiri dari
	| dua parameter yaitu fungsi pagination sebagai query dan paginationNumber sebagai
	| penomoran halaman
	| $name sebagai parameter nama pemanggilan get halaman
	| $number sebagai jumlah pembagian perhalaman
