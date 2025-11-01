# 🌈 BAB 8 — Background, Gradien, dan Gambar

## 8.1 Properti Dasar Background
| Properti | Fungsi | Contoh |
|-----------|---------|--------|
| `background-color` | Warna latar belakang | `#f9fafb` |
| `background-image` | Gambar/gradien latar | `url(bg.png)` |
| `background-repeat` | Pengulangan gambar | `no-repeat` |
| `background-size` | Ukuran gambar | `cover`, `contain` |
| `background-position` | Posisi gambar | `center`, `top left` |
| `background-attachment` | Efek scroll | `fixed`, `scroll` |

Contoh:
```css
.hero {
  background-color: #2563eb;
  background-image: url('banner.jpg');
  background-size: cover;
  background-position: center;
  color: #fff;
}
```

---

## 8.2 Gradien Linier
```css
.gradient {
  background: linear-gradient(90deg, #2563eb, #9333ea);
}
```
- `linear-gradient(arah, warna1, warna2, ...)`
- `to right`, `to bottom`, atau `45deg` untuk arah

---

## 8.3 Gradien Radial
```css
.radial {
  background: radial-gradient(circle, #facc15, #f97316);
}
```

---

## 8.4 Gabungan Gambar & Warna
```css
.hero {
  background: linear-gradient(to bottom, rgba(0,0,0,.5), rgba(0,0,0,.7)),
              url('header.jpg');
  background-size: cover;
  background-position: center;
}
```
> 💡 Teknik ini sering digunakan untuk *overlay teks di atas gambar.*

---

## 8.5 Multiple Backgrounds
```css
.box {
  background:
    url("pattern.svg") repeat,
    linear-gradient(135deg, #e0f2fe, #f0f9ff);
}
```

---

## 8.6 Background Attachment
```css
.parallax {
  background-image: url('mountain.jpg');
  background-size: cover;
  background-attachment: fixed;
}
```
> Efek *parallax scrolling* sederhana tanpa JavaScript.

---

## 8.7 Opacity & Overlay
```css
.overlay {
  position: relative;
}
.overlay::after {
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0,0,0,0.4);
}
```

---

## 8.8 Contoh Mini: Hero Section
```html
<section class="hero">
  <h1>Belajar CSS Background</h1>
  <p>Gabungkan warna, gambar, dan efek gradien untuk tampilan modern.</p>
</section>
```
```css
.hero {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height: 60vh;
  text-align: center;
  color: white;
  background: linear-gradient(to right, #2563eb, #9333ea);
}
.hero h1 { font-size: 2rem; margin-bottom: .5rem; }
.hero p { font-size: 1.1rem; opacity: .9; }
```

---

## 8.9 Tips Desain Background
- Gunakan **gradien lembut** untuk tampilan profesional.  
- Hindari kontras terlalu tinggi antara teks dan gambar.  
- Gunakan `rgba()` untuk overlay transparan.  
- Untuk performa: kompres gambar (`.webp`) dan aktifkan cache.

---

<div align="left">

🔗 [← Kembali ke Bab 7: Grid Layout](./07-grid-layout.md)

</div>
<div align="right">

🔗 [Lanjut ke Bab 9 → Transition & Animation](./09-transition-animation.md)

</div>
