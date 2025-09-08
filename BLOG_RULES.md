# MDX Blog Rules & Template

Dokumen ini menjelaskan aturan MDX yang diterima oleh sistem blog di proyek ini, serta menyediakan template siap pakai.

## Struktur Sumber Konten

Blog diambil dari repo GitHub eksternal:

- Repo: nfahrisalim/PersonalArchive
- Path: `Blog/[slug]/index.mdx`
- Satu post = satu folder. Nama folder = slug artikel.
- Opsional: sertakan gambar banner di folder yang sama bernama "Banner" (format apa pun: png/jpg/jpeg/gif/webp). Contoh: `Banner.png`.

Jika tidak ada file Banner, sistem akan menggunakan field `image` pada frontmatter sebagai cover.

## Frontmatter yang Didukung

Gunakan YAML di bagian teratas file `index.mdx`:

```yaml
---
# Wajib/Disarankan
title: "Judul Artikel"
description: "Ringkasan singkat artikel"  # disarankan
date: "2025-09-08"  # format tanggal apa pun yang valid (ISO disarankan)

# Opsional
updatedAt: "2025-09-09"  # tanggal update
author: "Naufal"         # default: Naufal jika tidak diisi
tags:
  - Technology
  - Next.js
image: "https://…/cover.jpg"  # fallback jika tidak ada Banner.* di folder
featured: false                  # opsional; saat ini tidak dipakai di API listing
---
```

Catatan:

- `date` dipakai sebagai `publishedAt`. Pastikan valid agar tidak fallback ke tanggal saat ini.
- `tags` harus berupa array string.
- `featured` saat ini tidak wajib dan tidak dibaca API listing; listing akan memilih featured pertama jika ada, jika tidak ambil post pertama.
- `readingTime` dihitung otomatis dari konten; tidak perlu diisi.

## Konten MDX yang Didukung

- Markdown umum + GFM (tables, strikethrough, task list) aktif.
- Heading (#, ##, ###, …) otomatis diberi id anchor dan dipakai untuk Table of Contents (TOC).
- Link eksternal otomatis dibuka di tab baru.
- Code/Pre ditata (tanpa highlighter khusus).

### Gambar di Konten

Anda bisa memasukkan gambar dengan dua cara:

1. Markdown biasa (direkomendasikan untuk relatif ke folder post):

   ```md
   ![Alt text](./diagram.png)
   ```

1. Komponen Next Image:

   ```mdx
   <Image src="https://example.com/img.jpg" alt="Deskripsi" width={1200} height={630} />
   ```

Aturan gambar:

- Jika `src` diawali `./`, sistem akan meresolusi menjadi `/blogs/[slug]/<nama-file>` saat render. Untuk bisa tampil, pastikan gambar tersedia di situs ini pada path `public/blogs/[slug]/<nama-file>` atau gunakan URL absolut/eksternal.
- Cover ideal: 1200×630 (digunakan di listing dan halaman detail).

## Template MDX Siap Pakai

Salin, ganti nilai sesuai kebutuhan, dan simpan sebagai `Blog/[slug]/index.mdx` di repo `PersonalArchive` Anda.

```mdx
---
title: "Memulai dengan Next.js dan MDX"
description: "Panduan singkat mengatur blog MDX dengan cover dan TOC"
date: "2025-09-08"
updatedAt: "2025-09-09"
author: "Naufal"
tags:
  - Technology
  - Next.js
image: "https://images.example.com/cover-next-mdx.jpg"  # hapus jika memakai Banner.png di folder
featured: false
---

# Memulai
Tuliskan paragraf pembuka di sini. TOC akan dibuat dari heading (H2/H3).

## Instalasi
Langkah instalasi singkat.

### Persiapan
Detail persiapan.

## Menambahkan Gambar
Gambar relatif dari folder post:

![Diagram Arsitektur](./diagram.png)

Atau gunakan komponen Image:

<Image src="https://images.example.com/ilustrasi.png" alt="Ilustrasi" width={1200} height={630} />

## Kode Contoh

```js
function hello() {
  console.log("Hello MDX")
}
```

## Tabel

| Fitur | Status |
|-------|--------|
| TOC   | OK     |
| GFM   | OK     |
```



## FAQ Cepat

- Judul/slug: jika `title` kosong, judul akan dibuat dari slug folder.
- Deskripsi: jika kosong, akan dibuat otomatis dari judul.
- Gambar cover: prioritas Banner.* di folder, lalu `image` di frontmatter, lalu fallback bawaan.

Jika butuh contoh konkret, buat folder baru di `PersonalArchive/Blog/` lalu unggah `index.mdx` sesuai template di atas dan opsional `Banner.png`.
