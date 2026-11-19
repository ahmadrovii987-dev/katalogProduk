# Katalog Produk — ROVII STORE

Aplikasi desktop manajemen etalase dan katalog produk berbasis **JavaFX** dan **SQLite**. Aplikasi ini menerapkan arsitektur **MVC (Model-View-Controller)** dengan pemisahan lapisan akses data (*Repository Pattern*) untuk mengelola data produk secara *real-time*.

## Fitur Utama

* **Tambah Produk (Create):** Menyimpan data produk baru (nama, harga, dan pilihan foto) ke database SQLite dengan validasi input.
* **Tampilan Etalase (Read):** Menampilkan daftar produk dalam bentuk kartu visual lengkap dengan penghitung total produk secara otomatis.
* **Ubah Data Produk (Update):** Memuat data produk terpilih ke form input untuk diperbarui, dilengkapi tombol batal edit.
* **Hapus Produk (Delete):** Menghapus data produk dari katalog dan database dengan dialog konfirmasi keamanan.
* **Pratinjau Input & Inisialisasi Otomatis:** Menampilkan pratinjau data saat pengisian form serta membuat file database `data/katalog.db` beserta tabelnya secara otomatis saat aplikasi pertama kali dijalankan.

## Teknologi yang Digunakan

* **Bahasa Pemrograman:** Java (JDK 21)
* **Antarmuka Pengguna (GUI):** JavaFX 21 (FXML & CSS)
* **Database:** SQLite (`sqlite-jdbc-3.49.1.0`)
* **Build Tool:** Apache Maven

## Struktur Proyek

```text
KatalogProduk/
├── src/
│   └── main/
│       ├── java/
│       │   ├── controller/
│       │   │   └── KatalogController.java   # Logika UI dan event handler CRUD
│       │   ├── data/
│       │   │   └── ProdukRepository.java    # Query SQL (INSERT, SELECT, UPDATE, DELETE)
│       │   ├── db/
│       │   │   └── Database.java            # Konfigurasi koneksi & pembuatan tabel SQLite
│       │   ├── main/
│       │   │   └── MainApp.java             # Entry point aplikasi JavaFX
│       │   └── model/
│       │       └── Produk.java              # Model entitas & validasi data produk
│       └── resources/
│           ├── image/                       # Aset gambar produk (roti.png, susu.png, kopi.png)
│           └── view/
│               ├── styles/
│               │   └── app.css              # Styling antarmuka aplikasi
│               └── katalog.fxml             # Tata letak antarmuka utama
├── pom.xml                                  # Konfigurasi dependensi Maven
└── README.md
```

## Cara Menjalankan Aplikasi

1. **Clone repository ini:**
   ```bash
   git clone [https://github.com/ahmadrovii987-dev/KatalogProduk.git](https://github.com/ahmadrovii987-dev/KatalogProduk.git)
   cd KatalogProduk
   ```

2. **Buka di IDE (NetBeans / IntelliJ IDEA / VS Code):**
   * Pastikan **JDK 21** dan **Maven** sudah terpasang.
   * Muat proyek sebagai *Maven Project* agar seluruh dependensi JavaFX dan SQLite JDBC terunduh otomatis.

3. **Jalankan Aplikasi:**
   * Jalankan file `main/MainApp.java` melalui IDE, atau gunakan perintah terminal:
     ```bash
     mvn clean javafx:run
     ```
