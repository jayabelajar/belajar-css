# 📱 BAB 10 — Responsive Design & Media Query

## 10.1 Apa itu Responsive Design?
**Responsive design** memastikan tampilan website tetap optimal di berbagai ukuran layar: HP, tablet, dan desktop.

> 🎯 Tujuan: membuat satu website yang bisa beradaptasi otomatis dengan resolusi layar.

---

## 10.2 Satuan Responsif
| Jenis | Contoh | Keterangan |
|--------|---------|------------|
| `vw`, `vh` | `50vw` = 50% dari lebar layar | Viewport unit |
| `em`, `rem` | `1em` = ukuran font parent, `1rem` = root | Relatif terhadap font |
| `%` | `width: 80%;` | Relatif terhadap elemen induk |

---

## 10.3 Viewport Meta Tag (Wajib)
Tambahkan di `<head>` HTML:
```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

---

## 10.4 Media Query Dasar
```css
@media (max-width: 768px) {
  .container {
    flex-direction: column;
  }
}
```

| Tipe Media | Contoh | Deskripsi |
|-------------|---------|-----------|
| `screen` | `@media screen and (min-width: 1024px)` | Layar |
| `print` | `@media print` | Mode cetak |
| `all` | `@media all` | Semua jenis media |

---

## 10.5 Breakpoint Umum
| Ukuran Perangkat | Rentang Lebar | Breakpoint |
|------------------|----------------|-------------|
| Mobile | ≤ 480px | `max-width: 480px` |
| Tablet | ≤ 768px | `max-width: 768px` |
| Laptop | ≤ 1024px | `max-width: 1024px` |
| Desktop | ≥ 1200px | `min-width: 1200px` |

---

## 10.6 Contoh Layout Responsif
```html
<div class="cards">
  <div class="card">A</div>
  <div class="card">B</div>
  <div class="card">C</div>
</div>
```

```css
.cards {
  display: flex;
  gap: 16px;
}
.card {
  flex: 1;
  background: hsl(220,83%,57%);
  color: #fff;
  padding: 20px;
  border-radius: 6px;
  text-align: center;
}

/* Responsif */
@media (max-width: 768px) {
  .cards { flex-direction: column; }
}
```

---

## 10.7 Gambar & Teks Responsif
```css
img { max-width: 100%; height: auto; }
h1 { font-size: clamp(1.5rem, 5vw, 2.5rem); }
```
> `clamp(min, preferred, max)` = fleksibel tapi tetap batas aman.

---

## 10.8 Container Query (CSS Modern)
```css
@container (max-width: 600px) {
  .card { flex-direction: column; }
}
```
> 💡 Dukung di browser modern. Berguna untuk komponen responsif mandiri.

---

## 10.9 Dark Mode dengan Media Query
```css
@media (prefers-color-scheme: dark) {
  body { background: #0f172a; color: #f1f5f9; }
}
```

---

## 10.10 Tips Responsive Design
- Desain **mobile-first**, baru perbesar ke desktop.  
- Gunakan **flex/grid** agar mudah diatur ulang.  
- Hindari ukuran tetap (fixed width/height).  
- Gunakan `clamp()`, `%`, dan `vw` untuk skala otomatis.  

---

<div align="left">

🔗 [← Kembali ke Bab 9: Transition & Animation](./09-transition-animation.md)

</div>
<div align="right">

🔗 [Lanjut ke Rangkuman & Studi Kasus Portofolio](./11-studi-kasus-portofolio.md)

</div>
