1. **Menyiapkan Halaman (Multipage Setup)**

A. Struktur Berkas dan Kode
Halaman web disusun dengan struktur tiga file HTML utama yang terhubung ke satu file stylesheet CSS bersama:
* `index.html` (Beranda)
* `kegiatan.html` (Kegiatan)
* `daftar.html` (Daftar)
* `css/style.css` (Stylesheet Bersama)

B. Konfigurasi Dasar HTML
Pada ketiga file HTML, telah diterapkan aturan dasar sesuai ketentuan:

Pada ketiga file HTML, telah diterapkan aturan dasar sesuai ketentuan:
1. **Title Unik:** Memiliki elemen `<title>` yang berbeda pada setiap halaman untuk identifikasi tab browser (misal: "Beranda - IT Del", "Daftar Kegiatan - IT Del", "Form Pendaftaran - IT Del").
2. **Atribut Bahasa & Viewport:** Menggunakan `<html lang="id">` untuk mendukung aksesibilitas bahasa Indonesia serta tag `<meta name="viewport" content="width=device-width, initial-scale=1.0">` untuk responsivitas layar.
3. **Shared Stylesheet:** Semua halaman dihubungkan ke stylesheet bersama melalui tag `<link rel="stylesheet" href="css/style.css">`.

C. Catatan Pengamatan & Hasil Uji
Tindakan yang Dilakukan:Saya membuat tiga file HTML baru di folder proyek, yaitu index.html untuk halaman beranda, kegiatan.html untuk halaman kegiatan, dan daftar.html untuk halaman daftar.   Menambahkan judul (<title>) yang berbeda-beda di setiap file HTML supaya bisa dibedakan saat dibuka di tab browser. Memasang atribut bahasa Indonesia (lang="id") dan meta viewport di bagian <head> agar halaman rapi dan pas di layar HP maupun laptop. Menghubungkan ketiga halaman tersebut ke satu file CSS yang sama yaitu css/style.css agar gaya tampilannya seragam. Hasil Nyata (Actual Result):

Saat dijalankan menggunakan Live Server, ketiga halaman berhasil terbuka dengan mulus.

2. **NAVIGASI KONSISTEN**

A. Tindakan

Menyalin pola navigasi ke semua halaman (index.html, kegiatan.html, dan daftar.html) menggunakan elemen <nav aria-label="Navigasi utama">.

Menambahkan atribut aria-current="page" khusus pada halaman yang sedang aktif.

Melakukan pengujian navigasi dengan cara:
Mengklik semua tautan tujuan dari setiap halaman.

Memeriksa penandaan halaman aktif via DevTools.

Menguji tombol Back (Kembali) dan Forward (Maju) pada browser.

B. Hasil Nyata

Semua jalur navigasi bekerja dengan lancar tanpa ada tautan yang rusak (404), penandaan aria-current berpindah sesuai halaman yang dibuka, serta fungsi navigasi riwayat browser (Back dan Forward) berjalan normal.

3. Path dan Asset

A. Penjelasan Jalur Berkas (Path Setup)Seluruh aset dan berkas pendukung pada situs web dipanggil menggunakan jalur relatif (relative path) berbasis web yang konsisten di ketiga halaman:   Stylesheet bersama: css/style.css   Berkas gambar/aset: assets/dog.jpg (atau nama aset gambar yang digunakan)

B. Aturan dan Konfigurasi Aset
Dalam pemanggilan berkas dan aset, telah diterapkan aturan sesuai ketentuan modul:
Penggunaan Relative Path: Memastikan tidak ada pemanggilan berkas yang menggunakan jalur lokal drive Windows (seperti C:\Users\...).
Kesesuaian Kapitalisasi (Case Sensitivity): Penulisan nama folder dan berkas pada kode HTML dibuat sama persis dengan nama berkas asli untuk mencegah error pada server web
Pemeriksaan Bebas 404: Seluruh aset diuji melalui DevTools tab Network untuk memastikan status pemuatan berkas sukses (200 OK).

C. Catatan Pengamatan & Hasil Uji
Tindakan yang Dilakukan:

Menghubungkan berkas CSS dan gambar menggunakan jalur relatif (css/style.css dan assets/...).
Memeriksa kesesuaian huruf besar dan kecil pada nama berkas di kode HTML dengan yang ada di folder proyek.
Membuka tab Network pada Developer Tools browser lalu merefresh halaman untuk mengecek status respon pemuatan berkas.

Hasil Nyata (Actual Result):

Seluruh aset gambar dan stylesheet berhasil termuat dengan lancar tanpa ada kode status error 404 Not Found
Gambar aset tampil dengan rapi pada layar browser tanpa broken image.
Penggunaan jalur relatif berjalan normal saat dipindahkan atau dijalankan via Live Server.

**6. Audit Keseluruhan**

#### **A. Penjelasan Audit & Integrasi**
Pada tahap ini, dilakukan audit menyeluruh terhadap ketiga halaman situs web (`index.html`, `kegiatan.html`, dan `daftar.html`) untuk memastikan responsivitas antarmuka, aksesibilitas keyboard, kevalidan kode HTML, serta kelancaran tautan antarhalaman sebelum dilakukan commit integrasi akhir.

#### **B. Aturan dan Langkah Audit**
1. **Aksesibilitas Keyboard:** Menguji semua elemen navigasi dan formulir agar dapat difokuskan serta diakses menggunakan tombol `Tab` dan `Enter`.
2. **Pengujian Responsivitas & Perbesaran:** Menguji tampilan situs pada lebar layar `320px` (layar HP), `1200px` (desktop), serta perbesaran (*zoom*) hingga 200%.
3. **Validasi HTML:** Memeriksa tidak adanya kesalahan sintaks pada berkas HTML.
4. **Pemeriksaan Tautan:** Memastikan seluruh tautan navigasi dan tombol berfungsi normal tanpa menghasilkan galat 404.

#### **C. Catatan Pengamatan & Hasil Uji**

* **Tindakan yang Dilakukan:**
  * Menavigasi situs menggunakan tombol `Tab` pada keyboard untuk menguji aksesibilitas focus ring pada elemen interaktif.
  * Membuka Developer Tools browser (`F12`), lalu menguji antarmuka pada tampilan `320px`, `1200px`, serta melakukan perbesaran layar (*zoom*).
  * Memeriksa seluruh tautan navigasi di setiap halaman untuk memastikan tidak ada *broken link*.
  * Melakukan commit integrasi ke Git setelah seluruh pengujian berhasil.

* **Hasil Nyata (Actual Result):**
  * Seluruh tombol dan menu navigasi dapat diakses penuh via keyboard.
  * Tampilan situs fleksibel dan rapi pada ukuran `320px`, `1200px`, serta saat di-zoom tanpa ada elemen yang saling bertumpukan.
  * Seluruh tautan terhubung dengan benar tanpa *broken link* atau pesan error `404 Not Found`.
  * Seluruh halaman terintegrasi dengan konsisten.

| Halaman | Kasus | Harapan | Hasil Nyata | Status / Bukti |
| :--- | :--- | :--- | :--- | :--- |
| **Semua Halaman** | Uji keyboard (`Tab` & `Enter`) | Elemen navigasi dan tombol dapat difokuskan & dibuka via keyboard | Focus ring berpindah lancar dan seluruh tautan dapat diakses | Berhasil (Lihat `bukti/`) |
| **`index.html`** | Uji layar 320px, 1200px, & Zoom | Tampilan beranda konsisten dan responsif di berbagai ukuran | Layout menyesuaikan lebar layar tanpa horizontal scroll berlebih | Berhasil (Lihat `bukti/`) |
| **`kegiatan.html`** | Uji layar 320px, 1200px, & Zoom | Konten dan gambar kegiatan tampil proporsional | Aset gambar dan teks tetap rapi di layar HP maupun desktop | Berhasil (Lihat `bukti/`) |
| **`daftar.html`** | Uji layar 320px, 1200px, & Zoom | Formulir pendaftaran tetap rapi dan tidak tumpang tindih | Input field, radio button, dan tombol submit mudah diakses | Berhasil (Lihat `bukti/`) |
| **Semua Halaman** | Validasi HTML | Kode HTML bebas dari kesalahan sintaks | Struktur HTML sesuai standar W3C tanpa pesan error | Berhasil (Lihat `bukti/`) |
| **Semua Halaman** | Pemeriksaan Tautan (*Link*) | Seluruh tautan navigasi berfungsi tanpa link gagal | Semua tautan terhubung lancar lintas halaman | Berhasil (Lihat `bukti/`) |

**8. Troubleshooting dan AI Use Statement**

#### **A. Tabel Troubleshooting**

| Gejala | Pemeriksaan / Solusi |
| :--- | :--- |
| **Halaman tidak berubah** | Simpan berkas (`Ctrl + S`), pastikan Live Server aktif, lalu *refresh* URL server yang benar di browser. |
| **404 Not Found** | Periksa kembali susunan path, lokasi folder, serta kapitalisasi nama berkas (huruf besar/kecil). |
| **CSS tidak cocok / tidak tampil** | Memastikan file CSS termuat di HTML, memeriksa kekeliruan *selector*, tata urutan *cascade*, serta memeriksa tab *Computed* pada DevTools. |
| **ReferenceError / SyntaxError** | Membaca baris error pada *Console* browser, memeriksa *scope* variabel, serta kelengkapan pasangan tanda kurung. |
| **Elemen null** | Memeriksa kembali penulisan *selector* JavaScript serta memastikan *script* dipanggil setelah DOM selesai dimuat. |
| **Data tidak sesuai** | Memeriksa alur *parsing* data, pengelolaan *state*, serta hasil *render* pada elemen HTML target. |

---

#### **B. AI Use Statement**

* **Alat AI yang Digunakan:** Gemini (Google AI)
* **Tujuan Penggunaan:** 
  * Penjelasan konsep pemograman web, navigasi git, serta diagnosa galat (*troubleshooting*).
  * Pembuatan draf struktur laporan `README.md` dan ringkasan langkah-langkah audit.
* **Bagian Bantuan:** 
  * Konsultasi penyelesaian kendala Git *merge conflict* dan konfigurasi repository.
  * Penyusunan format draf dokumentasi/laporan praktikum.
* **Verifikasi Hasil:**
  * Seluruh kode HTML, CSS, dan JavaScript diuji secara langsung menggunakan browser dan DevTools.
  * Solusi Git diverifikasi dan dijalankan mandiri melalui Terminal/CMD.
  * Tidak ada data rahasia, kata sandi (*password*), API *key*, maupun data sensitif mahasiswa yang dimasukkan ke dalam AI

> **Catatan Diagnosis Aman:**  
> Seluruh permasalahan teknis diselesaikan dengan melokalisasi sumber masalah, membaca pesan error/bukti pengujian, melakukan perbaikan pada satu penyebab spesifik, dan menjalankan pengujian ulang