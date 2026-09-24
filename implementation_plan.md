# Implementation Plan - Redesain & Peningkatan Visual Pembuktian_Anril.html

Meningkatkan visual dan pengalaman pengguna (UI/UX) pada aplikasi interaktif **Analisis Riil: Bab 1 (Pembuktian 3 Kolom)** agar terlihat sangat modern, elegan, profesional, dan memberikan kesan "WOW" layaknya platform edukasi kelas dunia (seperti Brilliant.org / Notion / Linear).

## User Review Required

> [!IMPORTANT]
> - **Retensi Logika & Data**: Seluruh logika JavaScript, penyimpanan progres (`window.storage`), fitur *clue budget*, dan data soal matematika akan tetap dipertahankan 100% tanpa mengubah alur kerja utama.
> - **Penambahan Tema**: Menambahkan fitur **Toggle Dark / Light Mode** agar pengguna nyaman belajar di malam maupun siang hari.
> - **Matematika & Tipografi**: Menggunakan font modern (*Plus Jakarta Sans* untuk UI, *EB Garamond* untuk kutipan/teorema, dan *JetBrains Mono* untuk rumus/skrip) serta mempercantik tampilan simbol-simbol matematika.

## Proposed Changes

#### [MODIFY] [Pembuktian_Anril.html](file:///c:/Users/THINKPAD%20X13/Vibes%20Codes/Pembuktian_Anril.html)

- **Sistem Desain (CSS Variables & Themes)**:
  - Membuat *palette* warna premium berbasis HSL (Deep Indigo `#4F46E5`, Violet `#7C3AED`, Emerald `#10B981`, Amber `#F59E0B`, Rose `#F43F5E`).
  - Efek *Glassmorphism* (kartu semi-transparan dengan `backdrop-filter: blur(12px)`), bayangan berlapis (*ambient micro-shadows*), dan sudut rounded yang konsisten (`border-radius: 14px`).
  - Mode Gelap (Dark Mode) & Light Mode dengan CSS variables dinamis.

- **Header & Navigation**:
  - Hero Header modern dengan *gradient text*, badge status interaktif, dan tombol *Theme Switcher* (Moon/Sun icon).
  - Mode Switcher bergaya *Segmented Control Pill* dengan indikator aktif yang mulus dan efek hover glow.

- **Sidebar (Daftar Soal)**:
  - Pengelompokan soal berdasarkan sub-bab (1.1 Himpunan & Fungsi, 1.2 Induksi Matematika, 1.3 Keterhitungan).
  - Kartu soal dengan indikator status/skor yang menyala (*glowing pill badge*), efek elevasi saat hover, dan penanda aktif yang jelas.

- **Panel Utama & Kartu Teorema**:
  - *Statement Card* dengan aksen *glowing left border*, background *soft gradient mesh*, dan aksen tipografi matematika yang jelas.
  - Kartu petunjuk (*tips*) dengan ikon dan tata letak yang bersih.

- **Mode Susun Ulang Bukti (Reorder Mode)**:
  - *Chip Langkah*: Kartu drag/click dengan *drag handle indicator*, efek *hover lift* (`transform: translateY(-2px)`), dan shadow halus.
  - *Slot Urutan*: Slot kosong dengan garis putus-putus beranimasi, dan slot terisi dengan animasi *feedback* warna (Hijau Emerald untuk benar, Merah Rose untuk salah).

- **Mode Latihan Mandiri (Practice Mode)**:
  - Area input *textarea* bergaya modern dengan *focus ring ring-glow*, counter baris yang rapi, serta tombol aksi (*+ Tambah Baris*, *Tampilkan Solusi*, *Tandai Selesai*) berdesain tombol *pill/rounded* modern.
  - Tampilan *Model Solution* dan *Hint/Clue System* bergaya kartu quest interaktif lengkap dengan *budget progress bar*.

- **Panel Nilai Akhir (Final Hero Score)**:
  - Ring skor besar dengan gradien melingkar / badge *glowing*, kartu statistik (Soal Selesai, Rata-rata Nilai, Clue Terpakai), dan tabel hasil dengan *progress bar* visual.

## Verification Plan

### Manual Verification
1. Buka `Pembuktian_Anril.html` di browser menggunakan `browser_subagent` atau peninjauan visual.
2. Uji alur **Susun Ulang Bukti**:
   - Memilih langkah dari pool ke slot.
   - Mengembalikan langkah ke pool.
   - Memeriksa urutan (tombol *Periksa Urutan*) dan memastikan animasi feedback (benar/salah) serta skor berfungsi dengan baik.
3. Uji alur **Latihan Mandiri**:
   - Menambah & menghapus baris.
   - Mengisi input premis & alasan.
   - Menampilkan hint/clue (memastikan batas budget 3 clue tetap berjalan).
   - Menandai selesai & memberikan rating.
4. Uji alur **Nilai Akhir**:
   - Memastikan ringkasan nilai dan statistik terhitung dengan akurat.
5. Uji **Dark Mode / Light Mode Toggle**:
   - Memastikan perpindahan tema berjalan mulus dan kontras warna tetap nyaman dibaca.
