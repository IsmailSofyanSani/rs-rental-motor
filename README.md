# RS Rental Motor Malang - Landing Page

Landing page statis untuk rental motor di Malang yang dioptimasi untuk SEO lokal, kecepatan loading, dan konversi via WhatsApp.

## 🚀 Fitur Utama

- ✅ **SEO Optimized** - Meta tags lengkap untuk ranking Google lokal Malang
- ✅ **Mobile-First Responsive** - Tampilan sempurna di semua perangkat
- ✅ **Fast Loading** - Menggunakan CDN Bootstrap dan optimasi WebP
- ✅ **WhatsApp Integration** - Direct conversion ke WhatsApp Admin
- ✅ **Modern UI/UX** - Desain menarik dengan animasi smooth
- ✅ **Zero Backend** - Sepenuhnya statis, hosting gratis

## 📁 Struktur Proyek

```
Landing Page RS Rental Motor/
├── index.html              # File utama website
├── assets/
│   ├── img/               # Folder untuk gambar motor (format WebP)
│   │   ├── honda-vario-125.webp
│   │   ├── honda-beat-street.webp
│   │   ├── yamaha-nmax.webp
│   │   ├── og-image.jpg   # Gambar untuk Open Graph
│   │   └── favicon.png    # Icon website
│   ├── css/               # CSS tambahan
│   │   └── custom.css
│   └── js/                # JavaScript tambahan (opsional)
└── README.md              # Dokumentasi ini
```

## 🛠️ Setup & Instalasi

### 1. Persiapan Gambar Motor

**PENTING:** Anda perlu menambahkan foto motor Anda sendiri ke folder `assets/img/`.

**Format yang direkomendasikan:**
- **Format**: WebP (untuk ukuran file minimal dengan kualitas tinggi)
- **Dimensi**: 800x600px atau 1200x900px
- **Nama file** (sesuaikan dengan yang ada di HTML):
  - `honda-vario-125.webp`
  - `honda-beat-street.webp`
  - `yamaha-nmax.webp`
  - `og-image.jpg` (untuk preview link di medsos, ukuran 1200x630px)
  - `favicon.png` (icon website, ukuran 32x32px atau 64x64px)

**Cara convert gambar ke WebP:**
- **Online**: Gunakan [Squoosh.app](https://squoosh.app/) atau [CloudConvert](https://cloudconvert.com/jpg-to-webp)
- **Tool**: Gunakan software seperti XnConvert atau Adobe Photoshop (Save As WebP)
- **Command Line** (jika punya ImageMagick):
  ```bash
  convert input.jpg -quality 85 output.webp
  ```

### 2. Ganti Nomor WhatsApp

Cari dan ganti nomor WhatsApp dummy dengan nomor Anda yang sebenarnya:

**Nomor dummy saat ini:** `6282131234567`

**Lokasi yang perlu diganti di `index.html`:**
1. Navbar - tombol "Hubungi Admin"
2. Hero Section - tombol "Chat Admin"
3. Sticky WhatsApp button (floating button)
4. Function `pesanViaWA()` di bagian JavaScript

**Cara mengganti:**
- Buka `index.html`
- Tekan `Ctrl+F` (Windows) atau `Cmd+F` (Mac)
- Cari: `6282131234567`
- Ganti semua dengan nomor WhatsApp Anda (format: 628XXXXXXXXXX tanpa +, -, atau spasi)

### 3. Sesuaikan Informasi Kontak

Edit bagian berikut di `index.html`:

```html
<!-- Footer Section -->
<p>
    <i class="bi bi-envelope-fill"></i>
    <a href="mailto:info@rsrentalmotor.com">info@rsrentalmotor.com</a>
</p>
<p>
    <i class="bi bi-geo-alt-fill"></i>
    Jl. Contoh No. 123, Malang, Jawa Timur
</p>
```

Ganti dengan alamat email dan alamat fisik rental Anda.

### 4. Update Google Maps Link

Cari link Google Maps di footer dan ganti dengan lokasi bisnis Anda:

```html
<a href="https://maps.google.com/?q=RS+Rental+Motor+Malang" target="_blank">
```

Ganti URL dengan link Google Maps lokasi Anda.

### 5. Sesuaikan Harga & Motor

Jika Anda ingin menambah/mengurangi motor atau mengubah harga:

1. Cari section `<!-- Katalog Armada -->`
2. Duplikasi atau edit card motor yang ada
3. Sesuaikan:
   - Nama motor
   - Harga sewa
   - Deskripsi fitur
   - Path gambar

## 🌐 Deployment ke Cloudflare Pages (GRATIS)

### Langkah-langkah Deploy:

1. **Buat Akun Cloudflare**
   - Kunjungi [dash.cloudflare.com/sign-up](https://dash.cloudflare.com/sign-up)
   - Daftar gratis dengan email Anda

2. **Upload ke GitHub** (Opsional tapi direkomendasikan)
   - Buat repository baru di GitHub
   - Upload semua file project ke repository
   - Atau gunakan direct upload di step berikutnya

3. **Deploy ke Cloudflare Pages**
   
   **Opsi A: Via GitHub (Otomatis)**
   - Login ke Cloudflare Dashboard
   - Pilih "Pages" di sidebar
   - Klik "Create a project"
   - Pilih "Connect to Git"
   - Hubungkan dengan GitHub dan pilih repository Anda
   - Cloudflare akan otomatis deploy setiap kali ada update
   
   **Opsi B: Direct Upload (Manual)**
   - Login ke Cloudflare Dashboard
   - Pilih "Pages" di sidebar
   - Klik "Create a project"
   - Pilih "Direct Upload"
   - Drag & drop folder project Anda atau zip file
   - Klik "Deploy"

4. **Dapatkan URL Website**
   - Setelah deploy selesai, Anda akan mendapat URL seperti:
     `https://your-project-name.pages.dev`
   - Website langsung live dan bisa diakses!

5. **Custom Domain (Opsional)**
   - Jika punya domain sendiri (misal: www.rsrentalmotor.com)
   - Buka project di Cloudflare Pages
   - Pilih tab "Custom domains"
   - Tambahkan domain Anda dan ikuti instruksi DNS

## 🎨 Kustomisasi Lebih Lanjut

### Mengubah Warna Brand

Edit variabel CSS di bagian `:root` dalam `index.html`:

```css
:root {
    --primary-color: #28a745;      /* Warna hijau utama */
    --secondary-color: #218838;    /* Warna hijau hover */
    --dark-color: #212529;         /* Warna teks gelap */
    --light-bg: #f8f9fa;          /* Background terang */
}
```

### Menambah Motor Baru

Copy-paste kode card motor yang ada dan sesuaikan:

```html
<div class="col-md-6 col-lg-4">
    <div class="card motor-card">
        <div style="overflow: hidden;">
            <img src="assets/img/nama-motor-baru.webp" class="card-img-top" alt="Nama Motor">
        </div>
        <div class="card-body">
            <h5 class="card-title">Nama Motor Baru</h5>
            <div class="price">Rp XX.000</div>
            <div class="price-period">per hari</div>
            <p class="card-text text-muted">
                <i class="bi bi-check-circle-fill text-success"></i> Fitur 1<br>
                <i class="bi bi-check-circle-fill text-success"></i> Fitur 2<br>
                <i class="bi bi-check-circle-fill text-success"></i> Fitur 3
            </p>
            <button class="btn btn-pesan" onclick="pesanViaWA('Nama Motor Baru')">
                <i class="bi bi-whatsapp"></i> Pesan via WhatsApp
            </button>
        </div>
    </div>
</div>
```

### Menambah FAQ

Copy-paste kode accordion item dan sesuaikan:

```html
<div class="accordion-item">
    <h2 class="accordion-header">
        <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#faq6">
            <i class="bi bi-question-circle me-2"></i> Pertanyaan baru Anda?
        </button>
    </h2>
    <div id="faq6" class="accordion-collapse collapse" data-bs-parent="#faqAccordion">
        <div class="accordion-body">
            Jawaban untuk pertanyaan baru Anda.
        </div>
    </div>
</div>
```

## 📱 Testing

### Test di Browser Desktop
1. Buka `index.html` di browser
2. Coba klik semua tombol WhatsApp
3. Test semua link navigasi
4. Test accordion FAQ

### Test di Mobile
1. Buka Developer Tools (F12)
2. Toggle Device Toolbar (Ctrl+Shift+M)
3. Test berbagai ukuran layar (iPhone, Android)
4. Pastikan semua elemen responsive

### Test WhatsApp Integration
1. Klik tombol "Pesan via WhatsApp" di card motor
2. Pastikan membuka WhatsApp dengan pesan yang benar
3. Pastikan nomor WhatsApp sudah benar

## 🔍 SEO Checklist

- ✅ Meta title mengandung "Rental Motor Malang"
- ✅ Meta description optimized untuk keyword lokal
- ✅ Open Graph tags untuk share di sosmed
- ✅ Semantic HTML (header, main, section, footer)
- ✅ Alt text pada semua gambar
- ✅ Mobile-friendly responsive design
- ✅ Fast loading dengan CDN

### Tips SEO Tambahan:

1. **Submit ke Google Search Console**
   - Daftar di [search.google.com/search-console](https://search.google.com/search-console)
   - Verifikasi website Anda
   - Submit sitemap

2. **Google My Business**
   - Buat profil bisnis di Google Maps
   - Link website Anda di profil
   - Minta review pelanggan

3. **Social Media**
   - Share link website di Instagram, Facebook
   - Gunakan link di bio Instagram
   - Preview akan muncul dengan gambar dari Open Graph

## 🐛 Troubleshooting

### Gambar tidak muncul
- Pastikan nama file gambar sesuai dengan yang di HTML
- Pastikan path gambar benar: `assets/img/nama-file.webp`
- Cek case sensitive (huruf besar/kecil harus sama)

### WhatsApp tidak terbuka
- Pastikan nomor WhatsApp format benar (628XXXXXXXXXX)
- Test di mobile device, karena desktop perlu WhatsApp Web
- Pastikan tidak ada karakter spasi atau tanda baca di nomor

### Website tidak responsive di mobile
- Clear browser cache (Ctrl+Shift+Delete)
- Test di mode incognito/private
- Pastikan viewport meta tag tidak diubah

### CSS tidak berubah setelah edit
- Clear browser cache
- Hard refresh (Ctrl+Shift+R atau Cmd+Shift+R)
- Pastikan tidak ada typo di CSS

## 📊 Analytics (Opsional)

Untuk tracking visitor, tambahkan Google Analytics:

1. Buat akun di [analytics.google.com](https://analytics.google.com)
2. Dapatkan tracking code
3. Tambahkan di `<head>` section index.html sebelum `</head>`:

```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

Ganti `GA_MEASUREMENT_ID` dengan ID Anda.

## 📞 Support

Jika ada pertanyaan tentang setup atau kustomisasi, Anda bisa:
- Edit langsung file HTML (mudah dibaca dan dimengerti)
- Gunakan browser DevTools untuk test perubahan CSS
- Lihat dokumentasi Bootstrap: [getbootstrap.com](https://getbootstrap.com)

## 📄 License

Project ini bebas digunakan untuk keperluan komersial rental motor Anda.

---

**Dibuat dengan ❤️ untuk RS Rental Motor Malang**

Semoga landing page ini membantu meningkatkan bisnis rental motor Anda! 🏍️
