# 🧮 BAB 7 — CSS Grid Layout

## 7.1 Apa itu CSS Grid?
**CSS Grid Layout** adalah sistem layout dua dimensi (baris & kolom) yang sangat fleksibel untuk membuat struktur halaman kompleks dengan mudah.

> 🎯 Tujuan: Mengatur elemen dalam *grid* (baris & kolom) tanpa perlu float atau positioning manual.

---

## 7.2 Membuat Grid Dasar
```html
<div class="grid">
  <div class="item">1</div>
  <div class="item">2</div>
  <div class="item">3</div>
  <div class="item">4</div>
</div>
```

```css
.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 12px;
}
.item {
  background: hsl(220,83%,57%);
  color: #fff;
  text-align: center;
  padding: 20px;
  border-radius: 6px;
}
```

---

## 7.3 Menentukan Kolom & Baris
```css
.grid {
  display: grid;
  grid-template-columns: 200px 1fr 2fr;
  grid-template-rows: auto 150px;
}
```

---

## 7.4 Fraksi (`fr`) dan Auto-fit
`fr` = *fractional unit* (bagian dari ruang yang tersedia)
```css
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
}
```
> 💡 Dengan `auto-fit` + `minmax()`, grid jadi **responsif otomatis**.

---

## 7.5 Spasi & Jarak
```css
.grid {
  gap: 20px; /* shorthand untuk row-gap & column-gap */
}
```

---

## 7.6 Menempatkan Elemen Grid
```css
.item1 {
  grid-column: 1 / 3; /* mulai kolom 1, sampai kolom ke-3 */
  grid-row: 1 / 2;
}
```

---

## 7.7 Grid Alignment
```css
.grid {
  display: grid;
  justify-items: center; /* horizontal */
  align-items: center; /* vertikal */
}
```

---

## 7.8 Template Area
```css
.grid {
  display: grid;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  grid-template-columns: 200px 1fr;
  gap: 12px;
}

.header { grid-area: header; background: #2563eb; }
.sidebar { grid-area: sidebar; background: #94a3b8; }
.main { grid-area: main; background: #e2e8f0; }
.footer { grid-area: footer; background: #475569; color: white; }
```

> Hasil: layout halaman modern dalam 10 baris CSS saja 🔥

---

## 7.9 Contoh: Layout Dasar Web
```html
<div class="layout">
  <header>Header</header>
  <aside>Sidebar</aside>
  <main>Konten Utama</main>
  <footer>Footer</footer>
</div>
```
```css
.layout {
  display: grid;
  grid-template-areas:
    "header header"
    "aside main"
    "footer footer";
  grid-template-columns: 200px 1fr;
  grid-template-rows: auto 1fr auto;
  height: 100vh;
}
header { grid-area: header; background: hsl(220,83%,57%); color:#fff; }
aside { grid-area: aside; background: #e2e8f0; }
main { grid-area: main; padding: 20px; }
footer { grid-area: footer; background: #1e293b; color:#fff; text-align:center; }
```

---

## 7.10 Tips CSS Grid
- Gunakan `auto-fit` untuk responsif otomatis.  
- Kombinasikan dengan `minmax()` agar grid fleksibel.  
- Gunakan `grid-template-areas` untuk layout kompleks yang mudah dibaca.  
- Jangan takut menggabungkan Grid + Flexbox (misalnya, header pakai Flexbox, isi pakai Grid).  

---

<div align="left">

🔗 [← Kembali ke Bab 6: Flexbox (Layout Modern)](./06-flexbox.md)

</div>
<div align="right">

🔗 [Lanjut ke Bab 8 → Background, Gradien, dan Gambar](./08-background-gradien.md)

</div>
