# 🎨 BAB 3 — Warna, Teks, dan Font

## 3.1 Warna dalam CSS
CSS mendukung berbagai format warna untuk fleksibilitas desain.

| Format | Contoh | Keterangan |
|---------|---------|------------|
| Hexadecimal | `#2563eb` | Format umum & singkat |
| RGB | `rgb(37, 99, 235)` | Campuran warna dasar |
| RGBA | `rgba(37, 99, 235, 0.8)` | Dengan transparansi |
| HSL | `hsl(220, 83%, 57%)` | Mudah disesuaikan visualnya |
| Nama warna | `blue`, `tomato` | 140+ nama bawaan CSS |

Contoh:
```css
body {
  background: hsl(0, 0%, 98%);
  color: #111827;
}
h1 {
  color: rgb(37, 99, 235);
}
p.note {
  color: rgba(0, 0, 0, 0.6);
}
```

---

## 3.2 Warna & Tema dengan Variabel CSS
```css
:root {
  --brand: hsl(220, 83%, 57%);
  --accent: hsl(14, 90%, 60%);
  --text: #111827;
  --bg: #fafafa;
}

body {
  background: var(--bg);
  color: var(--text);
}

a {
  color: var(--brand);
}
a:hover {
  color: var(--accent);
}
```
> 💡 Gunakan **CSS Variables** agar mudah membuat tema terang/gelap dan memelihara konsistensi warna.

---

## 3.3 Properti Teks Dasar
```css
h1, h2, h3 {
  font-weight: 600;
  color: var(--brand);
}

p {
  line-height: 1.6;
  text-align: justify;
  letter-spacing: 0.3px;
}

em { font-style: italic; }
strong { font-weight: bold; }
```

---

## 3.4 Font dan Tipografi
### Menggunakan Font Web
```css
body {
  font-family: "Inter", system-ui, sans-serif;
}
```

### Import Google Fonts
Tambahkan di `<head>` HTML:
```html
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap" rel="stylesheet">
```

---

## 3.5 Properti Font Umum
| Properti | Contoh | Fungsi |
|-----------|---------|--------|
| `font-family` | `"Inter", sans-serif` | Jenis huruf |
| `font-size` | `16px`, `1rem` | Ukuran teks |
| `font-weight` | `400`, `700`, `bold` | Ketebalan huruf |
| `font-style` | `italic`, `normal` | Gaya tulisan |
| `line-height` | `1.5` | Jarak antar baris |
| `letter-spacing` | `0.5px` | Spasi antar huruf |

---

## 3.6 Dekorasi Teks
```css
a {
  text-decoration: none;
}
a:hover {
  text-decoration: underline;
}

.uppercase { text-transform: uppercase; }
.capitalize { text-transform: capitalize; }

.shadow-text {
  text-shadow: 1px 2px 4px rgba(0, 0, 0, 0.1);
}
```

---

## 3.7 Contoh Mini: Heading & Paragraph
```html
<h1>Belajar CSS3</h1>
<h2>Styling Modern</h2>
<p>Dengan CSS, tampilan website menjadi lebih menarik dan responsif.</p>
```
```css
body { font-family: "Inter", sans-serif; color: #111; }
h1 { color: hsl(220, 83%, 57%); margin-bottom: 0; }
h2 { color: hsl(220, 20%, 40%); margin-top: 4px; }
p { font-size: 1rem; line-height: 1.6; }
```

---

## 3.8 Tips Desain Teks
- Gunakan **line-height ≥ 1.5** untuk keterbacaan.  
- Hindari terlalu banyak font-family; maksimal 2–3.  
- Gunakan warna kontras tinggi untuk teks utama.  
- Gunakan **em/rem** untuk ukuran relatif agar responsif.  

---

<div align="left">

🔗 [← Kembali ke Bab 2: Selektor, Properti, dan Nilai](./02-selektor-properti-nilai.md)

</div>
<div align="right">

🔗 [Lanjut ke Bab 4 → Box Model & Spacing](./04-box-model.md)

</div>
