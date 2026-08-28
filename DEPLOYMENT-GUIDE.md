# 🚀 Panduan Deployment ke Cloudflare Pages

Panduan lengkap step-by-step untuk deploy landing page RS Rental Motor ke Cloudflare Pages (GRATIS selamanya).

## 📋 Persiapan Sebelum Deploy

### ✅ Checklist Sebelum Upload

Pastikan Anda sudah:

- [ ] Menambahkan semua foto motor ke folder `assets/img/`
- [ ] Mengganti nomor WhatsApp dummy dengan nomor Anda
- [ ] Update informasi kontak (email, alamat)
- [ ] Update link Google Maps
- [ ] Test website di browser lokal
- [ ] Test semua tombol WhatsApp berfungsi

---

## 🌐 Metode 1: Deploy via Direct Upload (Termudah)

### Langkah 1: Buat Akun Cloudflare

1. Kunjungi [dash.cloudflare.com/sign-up](https://dash.cloudflare.com/sign-up)
2. Daftar dengan email Anda (GRATIS)
3. Verifikasi email Anda
4. Login ke dashboard

### Langkah 2: Masuk ke Cloudflare Pages

1. Di dashboard Cloudflare, cari menu **"Workers & Pages"** di sidebar kiri
2. Klik tab **"Pages"**
3. Klik tombol biru **"Create a project"**

### Langkah 3: Upload Project

1. Pilih **"Direct Upload"** (tab kedua)
2. Buat ZIP file dari folder project Anda:
   
   **Windows:**
   - Klik kanan folder "Landing Page RS Rental Motor"
   - Pilih "Send to" → "Compressed (zipped) folder"
   
   **Mac:**
   - Klik kanan folder "Landing Page RS Rental Motor"
   - Pilih "Compress"
   
3. **PENTING:** Jangan zip folder induknya, tapi zip isi foldernya!
   
   ✅ **BENAR** - Struktur dalam ZIP:
   ```
   rental-motor.zip
   ├── index.html
   ├── assets/
   ├── README.md
   └── sitemap.xml
   ```
   
   ❌ **SALAH** - Jangan seperti ini:
   ```
   rental-motor.zip
   └── Landing Page RS Rental Motor/
       ├── index.html
       └── assets/
   ```

4. Drag & drop file ZIP ke area upload, atau klik "Select from computer"
5. Tunggu upload selesai (biasanya cepat, tergantung ukuran gambar)

### Langkah 4: Setup Project

1. **Project name:** Masukkan nama project (contoh: `rs-rental-motor-malang`)
   - Nama ini akan jadi bagian dari URL: `rs-rental-motor-malang.pages.dev`
   - Gunakan huruf kecil dan tanda hubung (-)
   - Nama harus unik (belum dipakai orang lain)

2. **Production branch:** Biarkan default

3. Klik **"Deploy site"**

### Langkah 5: Website Live! 🎉

1. Tunggu proses deployment selesai (1-2 menit)
2. Anda akan mendapat URL seperti: `https://rs-rental-motor-malang.pages.dev`
3. Klik URL untuk membuka website Anda
4. Website sudah LIVE dan bisa diakses siapa saja!

### Langkah 6: Update Website (Jika Ada Perubahan)

Jika Anda ingin update website (ganti gambar, ubah harga, dll):

1. Login ke Cloudflare Dashboard
2. Masuk ke Pages → pilih project Anda
3. Klik tab **"Deployments"**
4. Klik tombol **"Create deployment"**
5. Upload ZIP file yang baru
6. Website akan otomatis update!

---

## 🔗 Metode 2: Deploy via GitHub (Untuk Auto-Update)

Metode ini lebih advanced, tapi memungkinkan auto-deploy setiap kali Anda push update.

### Langkah 1: Upload ke GitHub

1. Buat akun di [github.com](https://github.com) (jika belum punya)

2. Buat repository baru:
   - Klik tombol "+" di kanan atas → "New repository"
   - Repository name: `rs-rental-motor-malang`
   - Pilih **Public** (gratis) atau Private (jika premium)
   - **JANGAN** centang "Add a README file"
   - Klik "Create repository"

3. Upload files ke GitHub:
   
   **Via GitHub Web Interface (Mudah):**
   - Di halaman repository baru, klik "uploading an existing file"
   - Drag & drop semua file dan folder project Anda
   - Scroll ke bawah, klik "Commit changes"
   
   **Via Git Command (Advanced):**
   ```bash
   cd "Landing Page RS Rental Motor"
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/USERNAME/rs-rental-motor-malang.git
   git push -u origin main
   ```

### Langkah 2: Connect GitHub ke Cloudflare Pages

1. Login ke Cloudflare Dashboard
2. Masuk ke **Workers & Pages** → **Pages**
3. Klik **"Create a project"**
4. Pilih **"Connect to Git"**
5. Klik **"Connect GitHub"**
6. Authorize Cloudflare untuk akses GitHub Anda
7. Pilih repository `rs-rental-motor-malang`
8. Klik **"Begin setup"**

### Langkah 3: Configure Build Settings

1. **Project name:** Biarkan default atau sesuaikan
2. **Production branch:** `main`
3. **Build settings:**
   - Framework preset: **None** (karena static HTML)
   - Build command: (kosongkan)
   - Build output directory: `/`
4. Klik **"Save and Deploy"**

### Langkah 4: Website Live!

1. Tunggu deployment selesai
2. Website Anda sudah online!
3. **BONUS:** Setiap kali Anda push update ke GitHub, Cloudflare otomatis deploy versi terbaru!

---

## 🎨 Custom Domain (Opsional)

Jika Anda punya domain sendiri (misal: `www.rsrentalmotor.com`):

### Langkah 1: Tambah Custom Domain

1. Di Cloudflare Pages project Anda
2. Klik tab **"Custom domains"**
3. Klik **"Set up a custom domain"**
4. Masukkan domain Anda (contoh: `rsrentalmotor.com`)

### Langkah 2: Update DNS

Anda akan diminta update DNS record. Ada 2 cara:

**Opsi A: Domain sudah di Cloudflare**
- Cloudflare akan otomatis setup DNS
- Klik "Activate domain"
- Selesai!

**Opsi B: Domain di provider lain (Niagahoster, Hostinger, dll)**
- Buka panel domain provider Anda
- Tambah DNS record:
  - Type: **CNAME**
  - Name: **www** (atau @ untuk root domain)
  - Value: **rs-rental-motor-malang.pages.dev**
  - TTL: **Auto** atau **3600**
- Save changes
- Tunggu propagasi DNS (15 menit - 24 jam)

### Langkah 3: Aktifkan HTTPS

- HTTPS otomatis diaktifkan oleh Cloudflare (SSL gratis)
- Tunggu beberapa menit untuk sertifikat SSL aktif
- Test dengan buka `https://www.rsrentalmotor.com`

---

## 📊 Setup Google Analytics (Opsional)

Untuk tracking berapa visitor website Anda:

### Langkah 1: Buat Google Analytics Account

1. Kunjungi [analytics.google.com](https://analytics.google.com)
2. Sign in dengan akun Google
3. Klik "Start measuring"
4. Buat account baru dan property

### Langkah 2: Dapatkan Tracking ID

1. Setelah setup, Anda dapat **Measurement ID** (format: G-XXXXXXXXXX)
2. Copy Measurement ID ini

### Langkah 3: Tambahkan ke Website

1. Buka file `index.html`
2. Cari baris `</head>`
3. Tambahkan kode ini SEBELUM `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

4. Ganti `G-XXXXXXXXXX` dengan Measurement ID Anda
5. Save dan deploy ulang website

### Langkah 4: Verifikasi

1. Buka website Anda di browser
2. Buka Google Analytics dashboard
3. Cek "Realtime" → Anda harus muncul sebagai visitor
4. Selesai! Analytics aktif.

---

## 🔍 Submit ke Google Search Console

Agar website muncul di hasil pencarian Google:

### Langkah 1: Verifikasi Website

1. Kunjungi [search.google.com/search-console](https://search.google.com/search-console)
2. Sign in dengan akun Google
3. Klik "Add property"
4. Pilih **"URL prefix"**
5. Masukkan URL website: `https://rs-rental-motor-malang.pages.dev`

### Langkah 2: Verifikasi Ownership

Pilih metode verifikasi **"HTML tag"**:

1. Copy meta tag yang diberikan
2. Paste di `index.html` di dalam `<head>`
3. Deploy ulang website
4. Kembali ke Search Console, klik "Verify"

### Langkah 3: Submit Sitemap

1. Di Search Console, buka menu **"Sitemaps"**
2. Masukkan: `sitemap.xml`
3. Klik "Submit"
4. Google akan mulai crawl website Anda

### Langkah 4: Request Indexing

1. Buka menu **"URL Inspection"**
2. Masukkan URL halaman Anda
3. Klik **"Request indexing"**
4. Google akan prioritaskan crawl halaman ini

---

## 📱 Promosikan Website

Setelah website live, saatnya promosi:

### Social Media

✅ **WhatsApp Business:**
- Set URL website di profil
- Kirim broadcast ke pelanggan lama
- Tambahkan link di status

✅ **Instagram:**
- Tambahkan link di bio
- Post story dengan link sticker
- Buat post grid dengan info "Link di bio"

✅ **Facebook:**
- Share link di Facebook Page
- Buat postingan promo dengan link
- Tambahkan CTA button "Rental sekarang"

✅ **Google My Business:**
- Update profil bisnis Anda
- Tambahkan link website
- Upload foto motor dari website

### Offline Marketing

- Cetak QR Code yang link ke website
- Pasang di stiker motor rental
- Tambahkan di kartu nama
- Cetak flyer dengan QR code

---

## ⚠️ Troubleshooting

### Website tidak bisa diakses setelah deploy

**Solusi:**
- Tunggu 5-10 menit setelah deployment
- Clear cache browser (Ctrl+Shift+Delete)
- Coba akses dari browser lain atau incognito mode
- Cek status deployment di Cloudflare Dashboard

### Gambar tidak muncul di website

**Penyebab & Solusi:**
- Path gambar salah → Pastikan path `assets/img/nama-file.webp`
- Nama file tidak match → Cek huruf besar/kecil harus sama persis
- File tidak ter-upload → Re-upload dan pastikan folder `assets/img/` ada dalam ZIP

### Custom domain tidak bisa diakses

**Solusi:**
- DNS belum propagasi → Tunggu 24 jam
- DNS setting salah → Double check CNAME record
- Test dengan tool: [whatsmydns.net](https://www.whatsmydns.net/)

### WhatsApp button tidak berfungsi

**Solusi:**
- Pastikan format nomor benar: `628XXXXXXXXXX`
- Test di mobile device (WhatsApp Web di desktop)
- Cek console browser (F12) untuk error JavaScript

### Website lambat loading

**Solusi:**
- Compress gambar → Target ukuran < 200KB per gambar
- Gunakan format WebP
- Test speed: [PageSpeed Insights](https://pagespeed.web.dev/)

---

## 💡 Tips Pro

### Performance Optimization

1. **Optimasi Gambar:**
   - Gunakan format WebP
   - Target file size: 100-200KB per foto
   - Dimensi maksimal: 1200px lebar

2. **Lazy Loading:**
   - Tambahkan `loading="lazy"` ke tag `<img>`
   - Browser akan load gambar saat user scroll

3. **Caching:**
   - Cloudflare otomatis cache static files
   - Website load lebih cepat dari visit kedua

### Security

1. **HTTPS:**
   - Selalu gunakan HTTPS (otomatis di Cloudflare)
   - Jangan gunakan link HTTP

2. **Update Regular:**
   - Update harga dan info motor berkala
   - Hapus motor yang sudah tidak tersedia

### SEO Best Practices

1. **Content Update:**
   - Update content minimal 1 bulan sekali
   - Tambah motor baru jika ada
   - Update FAQ dengan pertanyaan pelanggan

2. **Local SEO:**
   - Gunakan keyword "Malang" di content
   - Daftar di direktori bisnis lokal
   - Minta review dari pelanggan

3. **Backlinks:**
   - Share di forum lokal Malang
   - Guest post di blog travel Malang
   - Partner dengan hotel/penginapan

---

## 📞 Butuh Bantuan?

Jika ada masalah:

1. **Cloudflare Support:**
   - Dokumentasi: [developers.cloudflare.com/pages](https://developers.cloudflare.com/pages/)
   - Community: [community.cloudflare.com](https://community.cloudflare.com/)

2. **Bootstrap Docs:**
   - [getbootstrap.com/docs](https://getbootstrap.com/docs/5.3/getting-started/introduction/)

3. **General Web Dev:**
   - [MDN Web Docs](https://developer.mozilla.org/)
   - [W3Schools](https://www.w3schools.com/)

---

**Selamat! Website Anda sudah online dan siap menerima customer! 🎉🏍️**

Happy renting! 🚀
