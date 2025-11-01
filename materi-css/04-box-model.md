# 🧱 BAB 4 — Box Model & Spacing

## 4.1 Konsep Box Model
Setiap elemen HTML berbentuk kotak dengan empat lapisan:
```
+-------------------------+
|      margin             | ← jarak luar
|  +-------------------+  |
|  |     border        |  | ← garis tepi
|  | +---------------+ |  |
|  | |   padding     | |  | ← jarak isi & tepi
|  | | +-----------+ | |  |
|  | | | content   | | |  | ← isi (teks/gambar)
|  | | +-----------+ | |  |
|  | +---------------+ |  |
|  +-------------------+  |
+-------------------------+
```

---

## 4.2 Properti Utama
| Properti | Contoh | Keterangan |
|-----------|---------|------------|
| `margin` | `20px` / `20px 10px` | Jarak antar elemen |
| `padding` | `10px` / `10px 5px` | Ruang dalam elemen |
| `border` | `1px solid #ccc` | Garis tepi |
| `border-radius` | `8px` | Sudut membulat |
| `box-sizing` | `border-box` | Ukuran termasuk padding & border |

---

## 4.3 Contoh Implementasi
```html
<article class="card">
  <h2>Box Model CSS</h2>
  <p>Setiap elemen HTML memiliki margin, border, padding, dan konten.</p>
</article>
```

```css
.card {
  width: 300px;
  padding: 16px;
  margin: 24px auto;
  border: 2px solid #e5e7eb;
  border-radius: 10px;
  background: #fff;
  box-sizing: border-box;
}
.card h2 {
  margin-top: 0;
}
```

---

## 4.4 Shorthand Penulisan
```css
/* margin: atas kanan bawah kiri */
margin: 10px 20px 30px 40px;

/* padding: vertikal horizontal */
padding: 20px 10px;

/* border lengkap */
border: 1px solid #d1d5db;
```

---

## 4.5 Box Shadow
```css
.box {
  box-shadow: 0 4px 8px rgba(0,0,0,0.1);
}
```
> 💡 Efek bayangan untuk memberi kesan kedalaman visual.

---

## 4.6 Overflow & Visibility
```css
.content-box {
  width: 200px;
  height: 100px;
  overflow: auto; /* hidden / scroll / visible */
}
```

---

## 4.7 Contoh: Kartu Produk
```html
<div class="product">
  <img src="https://via.placeholder.com/300x200" alt="Produk">
  <h3>Nama Produk</h3>
  <p class="price">Rp 250.000</p>
</div>
```
```css
.product {
  width: 300px;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
  padding: 12px;
  box-shadow: 0 2px 6px rgba(0,0,0,.05);
  background: #fff;
  transition: transform .2s ease, box-shadow .2s ease;
}
.product:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 12px rgba(0,0,0,.1);
}
.price {
  color: hsl(220, 83%, 57%);
  font-weight: 600;
}
```

---

## 4.8 Tips Box Model Modern
- Gunakan `box-sizing: border-box` secara global.  
- Gunakan satuan relatif (`rem`, `%`) agar fleksibel.  
- Gunakan `max-width` daripada `width` tetap.  
- Gunakan variabel CSS untuk spacing standar (`--space-sm`, `--space-lg`).  

---

<div align="left">

🔗 [← Kembali ke Bab 3: Warna, Teks, dan Font](./03-warna-teks-font.md)

</div>
<div align="right">

🔗 [Lanjut ke Bab 5 → Position, Display, dan Float](./05-position-display-float.md)

</div>
