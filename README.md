# 📱 TaskApp - Aplikasi Pencatat Tugas Berbasis Jetpack Compose

Aplikasi pencatat tugas (*to-do list*) lokal yang ringan, cepat, dan responsif. Dibangun menggunakan **Jetpack Compose**, **MVVM Architecture**, **Unidirectional Data Flow (UDF)**, dan **StateFlow**.

---

## 👥 Identitas Kelompok
* **Azhar Rasyid Wisnadi** - `[23523051]`
* **Arya** - `[NIM]`
* **Yusuf** - `[NIM]`

---

## 🎯 Masalah, Pengguna & Solusi

* **Masalah:** Mahasiswa sering kali kesulitan melacak *deadline* tugas praktikum secara cepat. Banyak aplikasi pencatat tugas di pasaran yang terlalu kompleks, memerlukan proses *login*, atau membutuhkan koneksi internet hanya untuk mencatat hal sederhana.
* **Pengguna Sasaran:** Mahasiswa Informatika yang membutuhkan aplikasi pencatat tugas harian yang instan dan tanpa kendala *network/authentication*.
* **Solusi:** **TaskApp**, sebuah aplikasi pencatat tugas tunggal berbasis memori lokal yang sangat ringan. Aplikasi ini memungkinkan pengguna untuk langsung mencatat, mengubah status, dan menghapus tugas dalam satu layar responsif tanpa koneksi internet.

---

## ✨ Fitur Utama
1. **Tambah Tugas dengan Validasi:** Menambahkan tugas baru ke dalam daftar. Dilengkapi validasi logika bisnis untuk mencegah penginputan teks kosong/spasi.
2. **Ubah Status Selesai (Toggle Completion):** Menandai tugas yang telah selesai dengan kotak centang (*checkbox*) dan garis dicoret (*strikethrough*).
3. **Hapus Tugas:** Menghapus baris tugas tertentu secara permanen dari memori lokal berdasarkan ID unik.
4. **Adaptive Layout:** Tampilan antarmuka yang otomatis beradaptasi. Menyusun komponen secara vertikal (*Column*) pada mode *portrait* (<600dp) dan secara horizontal berdampingan (*Row*) pada mode *landscape* atau tablet (≥600dp).

---

## 🔄 Contoh Alur UDF (Unidirectional Data Flow) - Fitur Tambah Tugas

Aplikasi ini menerapkan pola **UDF** di mana *State* mengalir ke bawah dan *Event* mengalir ke atas:
