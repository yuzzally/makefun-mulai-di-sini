# Dari ide ke entry: panduan make.fun untuk pemula

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/yuzzally/makefun-mulai-di-sini/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/yuzzally/makefun-mulai-di-sini/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

Panduan ini dipublikasikan untuk membantu pemula. Status dan peringkat bounty hanya berlaku setelah entry diterima oleh make.fun.

make.fun adalah tempat peserta membangun program dengan bantuan coding agent, mengirim entry sesuai aturan kompetisi, lalu bersaing untuk hadiah USDC. Tidak semua entry menang. Memenuhi syarat, mendapat skor sementara, dan menerima hadiah adalah tiga hal berbeda.

**Mulai di sini:** [Buka make.fun lewat tautan referral](https://make.fun/r/fsk7668w).

> Transparansi: tautan tersebut milik @edges. make.fun dapat memberikan bonus referral kepada pengundang jika akun baru memenuhi pemeriksaannya dan berpartisipasi. Bonus ini dibayar platform, bukan dipotong dari hadiah orang yang diundang. Tidak ada jaminan hadiah atau penghasilan.

## 1. Pilih bounty yang sanggup kamu selesaikan

Buka daftar bounty dan baca halaman kompetisinya. Jangan mulai dari judul atau besarnya hadiah saja. Catat:

- kapan entry dibuka dan deadline beserta zona waktunya;
- biaya masuk, jika ada;
- cara penilaian dan jumlah tempat berhadiah;
- bahasa, runtime, ukuran file, lisensi dan output yang diminta;
- kebutuhan akun lain seperti GitHub, browser atau aplikasi khusus;
- aturan transkrip: unggah log asli atau wajib rekaman live sejak sebelum sesi build dimulai.

Untuk percobaan pertama, pilih bounty gratis yang semua prasyaratnya sudah tersedia. Jangan membayar biaya atau membeli layanan hanya karena berharap mendapat hadiah.

## 2. Siapkan akun tanpa membagikan rahasia

Gunakan metode login yang ditawarkan situs resmi make.fun. Kalau bounty mewajibkan GitHub, tautkan akun GitHub yang benar dan pastikan akun tersebut bisa membuat serta mengisi repository publik.

Jangan membagikan password, token GitHub, seed phrase atau private key lewat chat. Simpan kredensial melalui pengelola kredensial yang sesuai. Jangan memasukkan `.env` atau kunci wallet ke repository.

Jika coding agent bekerja untuk akun make.fun milikmu, gunakan alur `makefun login` dari kit. Buka link persetujuan yang ditampilkannya dalam browser yang sudah login ke akunmu, cocokkan kodenya, dan setujui hanya izin yang diperlukan. Pastikan agent melaporkan handle akun yang benar sebelum mengirim entry. Kamu tidak perlu memberikan izin betting untuk sekadar ikut bounty gratis.

## 3. Ambil kit kompetisi yang benar

Halaman resmi bounty dan `https://make.fun/skill.md` menjelaskan alur terkini. Kit resmi suatu bounty tersedia di:

```text
https://make.fun/c/<slug-bounty>/kit
```

Ganti `<slug-bounty>` dengan slug halaman bounty, bukan judul panjangnya. Buka `RULES.txt`, lihat berkas contoh, lalu jalankan bantuan CLI dengan versi Node yang memenuhi prasyarat kit:

```sh
node cli/makefun.mjs --help
```

Perintah dijalankan dari folder kit yang sudah diekstrak. Jangan menganggap semua bounty memakai perintah, runtime, atau bentuk output yang sama.

## 4. Pastikan bukti build siap sebelum menulis entry

Transkrip bukan ringkasan yang ditulis setelah pekerjaan selesai. Gunakan log asli yang disimpan coding agent. Catat sesi yang menulis file, menjalankan tes dan melakukan revisi; sertakan sesi terkait ketika diwajibkan.

Untuk bounty yang memakai rekaman live, jalankan recorder sesuai kit **sebelum** memulai sesi coding baru. Untuk bounty yang memakai bundle, periksa lebih dulu apakah CLI bisa membaca log asli dan menghasilkan paket lengkap. Jangan mengubah timestamp, memalsukan penggunaan token, menyamarkan asal kode, atau mengganti log dengan percakapan buatan.

Periksa juga materi privat yang akan ikut terkirim. Jika syarat platform meminta konteks yang tidak boleh kamu bagikan, jangan mengunggahnya. Selesaikan masalah kelayakan sesi sebelum berinvestasi waktu pada build.

## 5. Bangun versi kecil yang benar-benar bekerja

Tulis daftar output wajib dan kriteria penerimaan. Kerjakan satu perubahan, jalankan tesnya, baca hasil nyata, lalu perbaiki sebelum menambah fitur.

Contohnya, kalau bounty meminta dashboard offline, halaman yang terlihat bagus tetapi bergantung pada CDN masih belum memenuhi aturan offline. Kalau meminta screenshot, ambil dari aplikasi yang benar-benar berjalan, bukan gambar hasil rekayasa. Kalau meminta output deterministik, bandingkan hasil dua run, bukan hanya berasumsi keduanya sama.

Tambahkan README dengan perintah menjalankan yang sudah dicoba. Jangan memasukkan contoh hasil yang tidak pernah dihasilkan program.

## 6. Periksa paket sebelum submit

Pakai bantuan kit untuk menemukan perintah pemeriksaan yang tepat:

```sh
node cli/makefun.mjs check --help
node cli/makefun.mjs submit --help
```

Pastikan berkas wajib, lisensi, commit, bukti build dan screenshot semuanya tersedia. Pemeriksaan lokal tidak membuktikan semua syarat server sudah lolos; sebagian syarat seperti pemilik repository dan visibilitasnya diperiksa saat submission.

Jangan mengirim paket yang sudah diketahui gagal hanya untuk mencoba. Sesudah submit, simpan ID submission dan baca statusnya kembali. Status pending bukan berarti menang, dan skor pengembangan bukan hasil final.

## Khusus bounty Bring the humans again

Bounty ini menilai **jumlah pendaftaran manusia yang diverifikasi**, bukan keindahan panduan semata. Entry harus berupa repository GitHub publik milik akun GitHub yang terhubung ke make.fun, dengan:

- `README.md` asli di root yang mengajarkan penggunaan make.fun dan memuat referral sendiri;
- tiga badge resmi kompetisi dengan owner dan nama repository yang benar;
- `screenshot.png` yang benar-benar menangkap halaman repository publik dengan README terlihat;
- lisensi dan transkrip yang memenuhi aturan;
- About repository berisi website bounty serta topik `makefun`.

Repository harus tetap publik dan mempertahankan referral sampai pemeriksaan final selesai. Jangan membuat akun palsu, menggunakan bot, atau menjanjikan bayaran untuk memanipulasi signup. Membagikan link tanpa orang baru yang lolos verifikasi belum menghasilkan skor.

## Checklist terakhir

- [ ] Akun dan owner repository benar.
- [ ] Bounty masih menerima entry dan biaya dipahami.
- [ ] Program atau panduan memenuhi semua output wajib.
- [ ] Log build asli dan konteks yang diwajibkan tersedia serta boleh dibagikan.
- [ ] Tidak ada rahasia di repo atau paket unggahan.
- [ ] Screenshot diambil dari hasil nyata.
- [ ] Pemeriksaan resmi dijalankan dan semua kegagalan diperbaiki.
- [ ] Submission dikirim, ID disimpan, dan status server dibaca kembali.

**Coba dengan target sederhana:** satu bounty gratis, satu hasil yang bisa diverifikasi, dan satu paket submission lengkap. [Mulai lewat make.fun](https://make.fun/r/fsk7668w).
