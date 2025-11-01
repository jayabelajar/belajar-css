# 🧩 BAB 6 — Flexbox (Layout Modern)

## 6.1 Apa itu Flexbox?
**Flexbox (Flexible Box Layout)** digunakan untuk mengatur elemen dalam satu dimensi (horizontal atau vertikal) secara **fleksibel dan responsif**.

> 🎯 Tujuan: mempermudah penyusunan kolom dan baris tanpa float atau positioning rumit.

---

## 6.2 Dasar Flexbox
```css
.container {
  display: flex;
}
```

Setelah diaktifkan, setiap anak (`.item`) menjadi **flex item**.

---

## 6.3 Properti Flex Container
| Properti | Nilai Umum | Fungsi |
|-----------|-------------|--------|
| `flex-direction` | `row` / `column` | Arah item |
| `justify-content` | `flex-start`, `center`, `space-between`, `space-around`, `space-evenly` | Posisi horizontal |
| `align-items` | `flex-start`, `center`, `flex-end`, `stretch` | Posisi vertikal |
| `gap` | `16px` | Jarak antar item |
| `flex-wrap` | `wrap` | Membungkus item otomatis |

Contoh:
```css
.container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 16px;
}
```

---

## 6.4 Properti Flex Item
| Properti | Fungsi |
|-----------|---------|
| `flex` | Kombinasi grow, shrink, basis |
| `flex-grow` | Seberapa besar item melebar |
| `flex-shrink` | Seberapa item menyusut |
| `flex-basis` | Ukuran dasar item |
| `align-self` | Override `align-items` container |

Contoh:
```css
.item {
  flex: 1; /* grow 1, shrink 1, basis auto */
}
.item-large {
  flex: 2; /* dua kali lebih besar */
}
```

---

## 6.5 Contoh Layout Dasar
```html
<div class="container">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
</div>
```
```css
.container {
  display: flex;
  gap: 12px;
}
.item {
  flex: 1;
  background: hsl(220,83%,57%);
  color: white;
  text-align: center;
  padding: 20px;
  border-radius: 6px;
}
```

---

## 6.6 Flexbox Column
```css
.flex-column {
  display: flex;
  flex-direction: column;
  gap: 8px;
}
```

---

## 6.7 Centering dengan Flexbox
```css
.center {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
```
```html
<div class="center">
  <h1>Selamat Datang!</h1>
</div>
```

---

## 6.8 Flex Responsive Card
```html
<div class="card-wrapper">
  <div class="card">A</div>
  <div class="card">B</div>
  <div class="card">C</div>
</div>
```
```css
.card-wrapper {
  display: flex;
  gap: 16px;
  flex-wrap: wrap;
}
.card {
  flex: 1 1 200px;
  background: #fff;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  padding: 20px;
  text-align: center;
  box-shadow: 0 2px 6px rgba(0,0,0,.05);
}
```

---

## 6.9 Tips Flexbox
- Gunakan `gap` alih-alih `margin` antar item.  
- `flex: 1` = rata otomatis semua kolom.  
- Gunakan `flex-wrap: wrap` untuk responsivitas.  
- Kombinasikan dengan **media query** untuk layout adaptif.

---

<div align="left">

🔗 [← Kembali ke Bab 5: Position, Display, dan Float](./05-position-display-float.md)

</div>
<div align="right">

🔗 [Lanjut ke Bab 7 → Grid Layout](./07-grid-layout.md)

</div>
