# ✅ BAB 12 — Praktik Terbaik & Struktur CSS

## 12.1 Tujuan
Membuat stylesheet yang **rapi, konsisten, mudah dirawat**, dan **skalable** untuk proyek kecil maupun besar.

---

## 12.2 Arsitektur & Organisasi
- **Mobile-first**: mulai dari gaya untuk layar kecil, naikkan dengan `min-width`.
- **Layering logis**:
  1) **Base** (reset, box-sizing)  
  2) **Tokens** (variabel warna, spacing, radius)  
  3) **Utilities** (helper kecil: `.hidden`, `.sr-only`)  
  4) **Layout** (grid/flex/container)  
  5) **Components** (card, button, navbar)  
  6) **Overrides** (khusus halaman/variasi).
- Pisahkan file jika perlu: `base.css`, `tokens.css`, `layout.css`, `components.css`.

---

## 12.3 Penamaan & Selektor
- **Gunakan class**; hindari styling berbasis tag atau ID agresif.
- **BEM-ish**: `card`, `card__title`, `card--featured`.
- Hindari selektor berantai terlalu dalam (maks 3 level): `.a .b .c`.

---

## 12.4 Konsistensi dengan CSS Variables
```css
:root {
  --brand: hsl(220 83% 57%);
  --surface: #fff;
  --text: #0f172a;
  --muted: #64748b;
  --radius: 10px;
  --space-1: 8px;
  --space-2: 12px;
  --space-3: 16px;
}
```
> Gunakan variabel untuk warna/spacing/radius agar UI konsisten.

---

## 12.5 Reset Ringan & Box Sizing
```css
* { box-sizing: border-box; }
html, body { margin: 0; }
img { max-width: 100%; display: block; }
```

---

## 12.6 Utilitas Berguna
```css
.hidden { display: none !important; }
.sr-only { position:absolute; width:1px; height:1px; padding:0; margin:-1px; overflow:hidden; clip:rect(0,0,0,0); white-space:nowrap; border:0; }
.container { width: min(90vw, 960px); margin-inline: auto; }
```

---

## 12.7 Layout Modern: Flex & Grid
- Gunakan **Flex** untuk satu dimensi (row/column).  
- Gunakan **Grid** untuk dua dimensi (baris & kolom).  
- Manfaatkan `gap` alih-alih margin antar item.

---

## 12.8 Responsif & Aksesibilitas
- Skala tipografi dengan `clamp()` dan unit relatif (`em`, `rem`, `vw`).
- Media query: fokus pada **breakpoint konten** (kapan layout rusak), bukan angka device.
- Warna kontras tinggi; jangan hanya mengandalkan warna untuk informasi.
- Gunakan `prefers-reduced-motion` untuk kurangi animasi.

```css
@media (prefers-reduced-motion: reduce) {
  * { animation: none !important; transition: none !important; }
}
```

---

## 12.9 Performance
- Minimalkan repaint besar: gunakan `transform` untuk animasi (bukan `top/left`).
- Kompres CSS (minify) untuk produksi.
- *Lazy load* gambar; gunakan `.webp` bila cocok.
- Hapus CSS yang tidak dipakai (purge).

---

## 12.10 Quality & Maintainability Checklist
- [ ] Konsisten variabel & skala spacing  
- [ ] Tidak ada `!important` kecuali darurat  
- [ ] Selektor tidak berlebihan (>3 level)  
- [ ] Validasi CSS lulus (W3C)  
- [ ] Navigasi keyboard lancar (fokus terlihat)  
- [ ] Responsif di breakpoint utama  
- [ ] Komponen reusable (tidak “hard-coded” untuk satu halaman)  

---

## 12.11 Template Folder Sederhana
```
/assets/css/
  base.css
  tokens.css
  layout.css
  components.css
  pages/
    home.css
```

---

## 12.12 Penutup
Dengan fondasi ini, kamu siap membangun **UI cepat, rapi, dan profesional**.  
Selanjutnya, kembangkan **komponen** dan **design system** kecil sesuai kebutuhan proyek.

---

<div align="left">

🔗 [← Kembali ke Bab 11: CSS Variables](/11-css-variables.md)

</div>
<div align="right">

🔗 [Lanjut ke Studi Kasus Portofolio (HTML + CSS)](/studi-kasus-portofolio-css.html)

</div>
