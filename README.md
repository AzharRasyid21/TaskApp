# 📱 TaskApp - Aplikasi Pencatat Tugas Berbasis Jetpack Compose

Aplikasi pencatat tugas (*to-do list*) lokal yang ringan, cepat, dan responsif. Dibangun menggunakan **Jetpack Compose**, **MVVM Architecture**, **Unidirectional Data Flow (UDF)**, dan **StateFlow**.

---

## 👥 Identitas Kelompok
* **Azhar Rasyid Wisnadi** - `[23523051]`
* **Dianta Arya Zaki Hanif** - `[24523159]`
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

1. **UI Event:** Pengguna menekan tombol "Tambah Tugas" pada komponen `InputSection`. UI tidak mengolah data sendiri, melainkan menembakkan *event* ke ViewModel melalui referensi fungsi `viewModel::addTask`.
2. **Business Logic & Validation:** `TaskViewModel` mengambil nilai `inputText` dari *state*. Jika teks kosong, ViewModel memperbarui `errorMessage`. Jika teks valid, objek `Task` baru dibuat.
3. **State Update:** ViewModel memperbarui data secara *immutable* menggunakan `.update` dan `.copy()`, sehingga menciptakan objek `TaskUiState` baru di memori.
4. **Recomposition:** Component `TaskScreen` yang mengamati `uiState` via `collectAsStateWithLifecycle()` mendeteksi perubahan referensi memori data dan secara otomatis memicu proses *Recomposition* untuk menggambar daftar tugas terbaru di layar.

---

## 🤝 Pembagian Kontribusi Anggota

| Anggota | Peran & Tanggung Jawab | Berkas yang Dikerjakan |
| :--- | :--- | :--- |
| **Azhar Rasyid Wisnadi** | **Project Setup & Data Model**<br>• Inisialisasi proyek dan dependensi Gradle<br>• Perancangan struktur data `Task` & `TaskUiState`<br>• Konfigurasi *entry point* `MainActivity` | • `build.gradle.kts`<br>• `Task.kt`<br>• `MainActivity.kt` |
| **Sandi** | **Business Logic & State Management**<br>• Pembuatan `TaskViewModel`<br>• Penerapan Enkapsulasi & `StateFlow`<br>• Logika validasi form & manipulasi data | • `TaskViewModel.kt` |
| **[Dianta Arya Zaki Hanif]** | **UI Components & Adaptive Layout**<br>• Pembuatan `TaskScreen`, `InputSection`, `TaskListSection`<br>• Implementasi `collectAsStateWithLifecycle`<br>• Penanganan *breakpoint* layar (600dp) | • `TaskScreen.kt` |

---

## 🚀 Cara Menjalankan Proyek

1. **Clone Repository ini:**
   ```bash
