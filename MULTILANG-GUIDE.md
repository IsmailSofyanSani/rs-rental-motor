# 🌐 Panduan Menambahkan Multi-Bahasa

## ✅ Status Saat Ini

### File: **armada.html**
**Status: LENGKAP ✅ 100%**
- Navbar ✅
- Page Header ✅
- Filter Section ✅
- Price Tabs (otomatis via JS) ✅
- WhatsApp Buttons (otomatis via JS) ✅
- Footer ✅

### File: **index.html**
**Status: SEBAGIAN ⚠️ 60%**

**Sudah Ada:**
- Navbar ✅
- Hero Section ✅
- Stats Section ✅
- Keunggulan Section (via data-translate-key) ✅
- Motor Cards (price tabs via JS) ✅
- Button "Lihat Seluruh Armada" ✅

**Belum Ada:**
- Process Steps (4 langkah) ❌
- Price periods text ❌
- FAQ Section ❌
- Testimonials ❌
- Location Section ❌
- CTA Section ❌
- Syarat & Ketentuan ❌
- Footer lengkap ❌

### File: **tentang.html**
**Status: LENGKAP ✅ 95%**
- Semua section sudah ada atribut multi-bahasa
- Hanya footer yang perlu minor update

---

## 📝 Cara Menambahkan Atribut Multi-Bahasa

### Metode 1: Menggunakan `data-lang-id` dan `data-lang-en`

Untuk teks statis di HTML:

```html
<!-- SEBELUM -->
<h2>Pertanyaan yang Sering Diajukan</h2>

<!-- SESUDAH -->
<h2 data-lang-id="Pertanyaan yang Sering Diajukan" 
    data-lang-en="Frequently Asked Questions">
    Pertanyaan yang Sering Diajukan
</h2>
```

### Metode 2: Menggunakan `data-translate-key`

Untuk teks yang sudah ada dalam object `translations` di JavaScript:

```html
<!-- SEBELUM -->
<h5>Hubungi Admin</h5>

<!-- SESUDAH -->
<h5 data-translate-key="contact_admin">Hubungi Admin</h5>
```

---

## 🔧 Elemen yang Perlu Ditambahkan di index.html

### 1. Process Steps (4 Langkah)

Tambahkan ke setiap `<h5>` dan `<p>` di `.process-step`:

```html
<h5 data-translate-key="step_1_title">Pilih Motor</h5>
<p data-translate-key="step_1_desc">Temukan motor...</p>
```

Keys yang sudah ada di `translations`:
- `step_1_title`, `step_1_desc`
- `step_2_title`, `step_2_desc`
- `step_3_title`, `step_3_desc`
- `step_4_title`, `step_4_desc`

### 2. FAQ Section

Tambahkan `data-lang-id` dan `data-lang-en` ke setiap:
- Section title `<h2>`
- Subtitle `<p class="section-subtitle">`
- Setiap pertanyaan di `<button class="accordion-button">`
- Setiap jawaban di `<div class="accordion-body">`

### 3. Testimonials

Tambahkan ke:
- Section title dan subtitle
- Setiap testimonial text
- Nama dan role customer

### 4. Location Section

Tambahkan ke:
- Section title dan subtitle
- "Alamat Lengkap"
- "Jam Operasional"
- "Hubungi Kami"
- "Setiap Hari"
- "Petunjuk Arah"

### 5. CTA Section

```html
<h2 data-lang-id="Siap Jelajahi Malang?" 
    data-lang-en="Ready to Explore Malang?">
    Siap Jelajahi Malang?
</h2>
```

### 6. Syarat & Ketentuan

Tambahkan ke:
- Setiap kategori header
- Setiap list item di `<ul class="syarat-list">`

---

## 💡 Translation Keys yang Sudah Tersedia

Cek object `translations` di JavaScript untuk key yang bisa dipakai:

### Sudah Ada di translations object:
```javascript
// Sections
'why_choose', 'why_choose_desc'
'easy_steps', 'easy_steps_desc'
'best_motorcycles', 'best_motorcycles_desc'
'requirements_title', 'requirements_desc'
'testimonials_title', 'testimonials_desc'
'location_title', 'location_desc'
'faq_title', 'faq_desc'
'ready_explore', 'ready_explore_desc'
'chat_now'

// Process Steps
'step_1_title', 'step_1_desc'
'step_2_title', 'step_2_desc'
'step_3_title', 'step_3_desc'
'step_4_title', 'step_4_desc'

// Motor Features
'fuel_efficient', 'long_distance_comfort'
'spacious_trunk', 'agile', 'city_tour'
'fuel_saving', 'premium_stylish'
'powerful_engine', 'complete_features'

// Footer
'contact_us', 'operational'
'every_day', 'fast_response'
```

---

## 🚀 Contoh Implementasi Lengkap

### Example: FAQ Section

```html
<!-- Section Title -->
<h2 class="section-title" data-translate-key="faq_title">
    Pertanyaan yang Sering Diajukan (FAQ)
</h2>

<p class="section-subtitle" data-translate-key="faq_desc">
    Temukan jawaban atas berbagai pertanyaan umum...
</p>

<!-- FAQ Item -->
<div class="accordion-item">
    <h2 class="accordion-header">
        <button class="accordion-button" 
                data-lang-id="Bagaimana cara booking sewa motor?"
                data-lang-en="How to book a motorcycle rental?">
            Bagaimana cara booking sewa motor?
        </button>
    </h2>
    <div class="accordion-collapse collapse">
        <div class="accordion-body" 
             data-lang-id="Pemesanan dapat dilakukan melalui WhatsApp..."
             data-lang-en="Booking can be done via WhatsApp...">
            Pemesanan dapat dilakukan melalui WhatsApp...
        </div>
    </div>
</div>
```

---

## ✅ Checklist Progress

### index.html
- [x] Navbar
- [x] Hero Section
- [x] Stats
- [x] Keunggulan
- [x] Motor Cards
- [ ] Process Steps → **PERLU DITAMBAHKAN**
- [ ] Syarat & Ketentuan → **PERLU DITAMBAHKAN**
- [ ] FAQ → **PERLU DITAMBAHKAN**
- [ ] Testimonials → **PERLU DITAMBAHKAN**
- [ ] Location → **PERLU DITAMBAHKAN**
- [ ] CTA Section → **PERLU DITAMBAHKAN**
- [ ] Footer lengkap → **PERLU DITAMBAHKAN**

### armada.html
- [x] Semua section LENGKAP ✅

### tentang.html
- [x] Semua section LENGKAP ✅

---

## 📞 Jika Butuh Bantuan

Untuk menambahkan atribut multi-bahasa secara massal, ikuti pattern di atas atau minta bantuan untuk section tertentu yang spesifik.

**Prioritas Update:**
1. FAQ Section (paling sering dibaca)
2. Process Steps  
3. Testimonials
4. Location Section
5. Syarat & Ketentuan (panjang tapi penting)

