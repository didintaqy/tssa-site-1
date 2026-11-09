# Audit & Perbaikan — Tapak Suci Sport Academy Batam

**Situs:** https://sites.google.com/view/tapak-suci-sport-academy/halaman-muka
**Tanggal audit:** 9 November 2026
**Halaman diperiksa:** Halaman Muka, SISWA, GALERY, TENTANG TSSA

> Catatan: saya tidak bisa mengubah Google Sites secara langsung karena browser tidak dalam keadaan login ke akun Google pemilik situs. Karena itu hasil kerja dibagi dua: **laporan temuan** (dokumen ini) dan **versi perbaikan yang bisa langsung dilihat** (`index.html`).

---

## 1. Ringkasan skor

| Metrik | Sebelum | Sesudah (versi perbaikan) |
|---|---|---|
| SEO | **67** | **100** |
| Aksesibilitas | **89** | **100** |
| Best Practices | 100 | 100 |
| Meta description | ❌ tidak ada | ✅ ada |
| Alt text gambar | ❌ 0 dari 16 | ✅ semua gambar |
| Link kontak/eksternal | ❌ 0 | ✅ WhatsApp, alamat, Instagram |

---

## 2. Masalah kritis

### 2.1 Menu dan judul menimpa banner (tidak terbaca)
Di semua halaman, navigasi putih transparan diletakkan di atas foto banner yang ramai. Di halaman **TENTANG TSSA**, judul halaman raksasa `TAPAK SUCI SPORT ACADEMY` juga menimpa tulisan banner sehingga keduanya saling menutupi.

**Dampak:** pengunjung sulit membaca menu dan judul; kesan pertama terlihat berantakan.
**Bukti:** `docs/sebelum-tentang.jpg`, `docs/sebelum-galery.jpg`.

**Perbaikan:**
- Header dibuat solid (putih) dan *sticky*, teks menu gelap.
- Banner ditampilkan utuh tanpa teks HTML di atasnya.
- Judul halaman dipindah ke section di bawah banner.

### 2.2 Halaman SISWA kosong
Halaman SISWA hanya berisi kotak login `REMAJA` dengan area kosong sangat besar. Tidak ada penjelasan halaman itu untuk apa, siapa yang boleh masuk, atau bagaimana cara mendapat akun.

**Dampak:** pengunjung mengira situs rusak; calon siswa/orang tua bingung.
**Bukti:** `docs/sebelum-siswa.jpg`.

**Perbaikan yang disarankan:**
- Tambahkan judul + penjelasan singkat: "Portal Siswa — untuk melihat jadwal, absensi, dan materi latihan. Akun diberikan oleh admin akademi."
- Beri tombol "Kembali ke Halaman Muka" dan "Hubungi Admin" (WhatsApp).
- Jika portal belum siap, sembunyikan menu SISWA dari navigasi.

### 2.3 Tidak ada kontak sama sekali
Tidak ada satu pun link eksternal di seluruh halaman: tidak ada WhatsApp, telepon, email, Instagram, atau peta lokasi. Alamat hanya "MB2 Lantai GF — Sebelah Daihatsu" tanpa nama mal, nomor unit, atau kota.

**Dampak:** orang tua yang ingin mendaftar tidak punya cara menghubungi.
**Perbaikan:** section CTA "Gabung TSSA" + footer kontak + tombol WhatsApp.

### 2.4 Jadwal latihan saling bertentangan
Sabtu tercantum **15.00–17.00** *dan* **16.00–18.00**; Minggu juga sama. Tidak dijelaskan perbedaan keduanya.

**Dampak:** peserta datang di jam yang salah.
**Perbaikan sementara:** ditampilkan sebagai "dua kelompok waktu" dengan catatan untuk konfirmasi.
**Perlu keputusan Anda:** apakah ini dua kelompok usia, dua lokasi, atau salah ketik?

### 2.5 Semua gambar tanpa alt text
16 gambar di halaman muka dan 10 gambar di galeri memiliki `alt=""`.

**Dampak:** pembaca layar tidak bisa mendeskripsikan gambar; skor aksesibilitas turun; gambar tidak muncul di Google Images.
**Perbaikan:** alt text deskriptif untuk seluruh gambar.

### 2.6 Tidak ada meta description
Google menampilkan potongan teks acak di hasil pencarian.

**Perbaikan:** deskripsi 155 karakter + Open Graph untuk preview WhatsApp.

---

## 3. Masalah penting

| # | Temuan | Perbaikan |
|---|---|---|
| 3.1 | Typo **"KEJUARAAN DAERA 5"** | → **"Daerah 5"** |
| 3.2 | Typo **"UARA UMUM 1 - USIA DINI"** | → **"Juara Umum 1 — Usia Dini"** |
| 3.3 | "31 Emas 23 Perak 11 Perunggu" tanpa pemisah | → chip medali terpisah |
| 3.4 | Emoji 🥋📖🕌🏆 dipakai sebagai ikon; di beberapa perangkat tampil sebagai kotak kosong | → ikon SVG |
| 3.5 | Struktur heading tidak konsisten; halaman dalam tidak punya H1 | → hierarki H1 → H2 → H3 |
| 3.6 | Galeri tanpa keterangan foto dan ukuran tidak seragam | → grid seragam + caption |
| 3.7 | Halaman TENTANG hanya 2 paragraf, tanpa visi/misi, sejarah, atau struktur pelatih | → tambahkan bagian profil |
| 3.8 | Tidak ada info pendaftaran (alur, biaya, perlengkapan) | → section "Cara bergabung" |
| 3.9 | Gambar 250–340 KB tanpa `width`/`height` (layout bergeser saat memuat) | → atribut dimensi + `loading="lazy"` |
| 3.10 | Judul tab hanya "TSSA" | → judul deskriptif per halaman |

## 4. Masalah minor

- Footer masih menampilkan "Page updated / Report abuse" bawaan Google Sites.
- Tidak ada favicon khusus.
- Menu "TENTANG TSSA" punya panah dropdown, tetapi submenu tidak terlihat jelas.
- Tidak ada tautan ke Instagram/YouTube meskipun banyak foto kegiatan.
- Tidak ada informasi "sejak tahun berapa" / jumlah atlet aktif (bisa menambah kredibilitas).

---

## 5. Perbaikan yang sudah dibuat

File: **`index.html`** (satu halaman, tanpa dependensi build).

**Desain**
- Header putih solid + sticky, logo, menu gelap, CTA merah.
- Banner utuh tanpa teks menimpa, diikuti strip "Disiplin • Karakter • Prestasi".
- Section pembuka 2 kolom dengan foto dan badge "Pembinaan berkelanjutan".
- 4 kartu pilar dengan ikon SVG dan crop gambar seragam 4:3.
- Prestasi: 3 kartu statistik, kartu utama King of Silat, grid prestasi, dan blok O2SN.
- Jadwal: 3 kartu gelap dengan jam besar + kartu lokasi.
- **Cara bergabung: 4 langkah** (hubungi admin → sesi percobaan → pilih kelompok → administrasi).
- **Profil pelatih: 3 kartu** (placeholder, ganti dengan nama & foto resmi).
- CTA merah + footer 3 kolom.

**Teknis**
- `lang="id"`, meta description, canonical, Open Graph, JSON-LD `SportsOrganization`.
- Alt text deskriptif untuk 16 gambar; `width`/`height`; `loading="lazy"`.
- Fokus keyboard terlihat (`:focus-visible`), skip link, `aria-expanded` pada menu mobile.
- Responsif: 375 px, 912 px, dan desktop ≥1180 px tanpa scroll horizontal.
- Menghormati `prefers-reduced-motion`.

**Hasil Lighthouse (lokal):** Aksesibilitas 100 · Best Practices 100 · SEO 100.

---

## 6. Yang perlu Anda ganti sebelum dipakai

| Placeholder | Lokasi | Ganti dengan |
|---|---|---|
| `6287770600737` | tombol WhatsApp (2 tempat) | sudah diisi |
| `0877-7060-0737` | footer | sudah diisi |
| `@tapaksucisportacademybatam` | footer | sudah diisi |
| `@tapaksuci_sportacademy` | footer | sudah diisi |
| `MB2 Lantai GF, sebelah Daihatsu` | jadwal + footer | nama mal + nomor unit + kota |
| `9 Gelar Juara Umum 1` | kartu statistik | verifikasi ulang jumlah gelar |
| Jam Sabtu/Minggu | kartu jadwal | konfirmasi dua kelompok waktu |

---

## 7. Cara menerapkan ke Google Sites

Google Sites tidak mendukung impor HTML, jadi perbaikan dilakukan manual. Urutan yang paling berdampak:

1. **Perbaiki header/banner** (paling terlihat)
   - Buka halaman → klik banner → *Page settings* → ubah tipe header menjadi **Title only** atau **Cover**.
   - Pindahkan gambar banner ke body: *Insert → Image*, atur selebar halaman.
   - Jika tetap memakai banner: pilih tema dengan header berwarna solid agar menu terbaca.

2. **Tambahkan kontak**
   - *Insert → Button* → "Hubungi via WhatsApp" → tempel `https://wa.me/62xxxxxxxxxx`.
   - Tambahkan alamat lengkap dan Instagram di footer.

3. **Rapikan halaman SISWA**
   - Tambahkan paragraf penjelasan di atas form login, atau sembunyikan menu SISWA sampai portal siap.

4. **Perbaiki teks**
   - "DAERA 5" → "Daerah 5", "UARA UMUM 1" → "Juara Umum 1".
   - Samakan format prestasi: judul kejuaraan (tebal) + daftar gelar.

5. **Alt text gambar**
   - Klik gambar → menu gambar → **Alt text** → tulis deskripsi singkat.
   - Contoh: "Atlet TSSA meraih juara 1 O2SN SMP tingkat Provinsi Kepri".

6. **SEO**
   - Google Sites baru tidak menyediakan kolom meta description; Google mengambil otomatis dari paragraf pertama. Pastikan paragraf pembuka memuat "Tapak Suci Sport Academy Batam", "pencak silat", dan "Batam".
   - Ganti judul halaman dari "TSSA" menjadi "Tapak Suci Sport Academy Batam — Pencak Silat".

7. **Seragamkan galeri**
   - Gunakan grid 3 kolom, crop 4:3, dan tambahkan keterangan di bawah foto.

8. **Konsistensi warna**
   - Merah `#B3261E`, emas `#C99A2E`, krem `#FBF8F3`, teks `#16181D`.

---

## 8. Rekomendasi lanjutan

- Tambahkan section **"Cara Bergabung"** (4 langkah: hubungi admin → sesi percobaan → pilih kelompok → administrasi).
- Tambahkan **profil pelatih** (nama, sertifikasi) untuk membangun kepercayaan.
- Buat **halaman berita/prestasi** agar konten segar untuk SEO.
- Pertimbangkan **Google Form** untuk pendaftaran, lalu tautkan dari tombol CTA.
- Pasang **Google Analytics** untuk melihat halaman yang paling dicari.

---

## 9. Isi folder

```
tssa-fix/
├─ index.html          ← versi perbaikan (buka di browser)
├─ assets/             ← 16 gambar dari situs asli
├─ docs/               ← screenshot sebelum & sesudah
├─ server.js           ← server lokal opsional (node server.js)
└─ AUDIT.md            ← dokumen ini
```
