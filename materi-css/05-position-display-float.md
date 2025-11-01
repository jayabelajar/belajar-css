# 🧭 BAB 5 — Position, Display, dan Float

## 5.1 Display: Dasar Layout Elemen
Properti `display` menentukan **bagaimana elemen ditampilkan di halaman**.

| Nilai | Keterangan | Contoh |
|--------|-------------|--------|
| `block` | Elemen tampil penuh satu baris | `<div>`, `<section>` |
| `inline` | Tidak memulai baris baru | `<span>`, `<a>` |
| `inline-block` | Inline tapi bisa diatur lebar/tinggi | `<button>` |
| `flex` | Layout modern fleksibel (Bab 6) | `<div>` |
| `grid` | Layout 2D kompleks (Bab 7) | `<main>` |
| `none` | Sembunyikan elemen sepenuhnya | - |

Contoh:
```css
span { display: inline-block; width: 120px; }
```

---

## 5.2 Visibility vs Display
```css
.box1 { display: none; }   /* hilang total dari layout */
.box2 { visibility: hidden; } /* tetap ambil ruang */
```

---

## 5.3 Position: Mengatur Posisi Elemen
Properti `position` menentukan **bagaimana elemen ditempatkan** relatif terhadap dokumen atau elemen lain.

| Nilai | Deskripsi | Contoh Umum |
|--------|------------|-------------|
| `static` | Default, sesuai urutan dokumen | Semua elemen default |
| `relative` | Posisi relatif terhadap posisi awal | Tooltip sederhana |
| `absolute` | Posisi absolut terhadap parent `relative` | Popup, badge |
| `fixed` | Menempel di viewport | Navbar tetap |
| `sticky` | Hybrid antara relative & fixed | Header yang menempel saat scroll |

Contoh:
```css
.parent { position: relative; }
.badge {
  position: absolute;
  top: 8px;
  right: 8px;
  background: hsl(14,90%,60%);
  color: #fff;
  padding: 4px 8px;
  border-radius: 999px;
}
```

---

## 5.4 Z-Index: Urutan Tumpukan Elemen
```css
.modal { position: fixed; z-index: 999; }
.overlay { position: fixed; z-index: 500; }
```
> 💡 Semakin tinggi angka `z-index`, semakin di atas elemen lain (hanya berlaku jika `position` ≠ `static`).

---

## 5.5 Float & Clear
Sebelum Flex/Grid, layout kolom sering pakai `float`.

```css
.img-left {
  float: left;
  margin: 8px 16px 8px 0;
}
.clearfix::after {
  content: "";
  display: block;
  clear: both;
}
```

> ⚠️ Float sekarang jarang dipakai untuk layout utama.  
> Gunakan **Flexbox atau Grid** untuk hasil modern & responsif.

---

## 5.6 Contoh Praktis: Header Tetap
```html
<header class="navbar">Menu Utama</header>
<main>
  <p>Scroll halaman untuk melihat efek fixed...</p>
</main>
```
```css
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  background: hsl(220,83%,57%);
  color: #fff;
  padding: 12px 16px;
}
main { margin-top: 60px; }
```

---

## 5.7 Ringkasan
- `display` → bagaimana elemen ditampilkan  
- `position` → bagaimana elemen diposisikan  
- `float` → metode lama untuk kolom (hindari jika bisa)  
- Gunakan `z-index` untuk tumpukan layer  

---

<div align="left">

🔗 [← Kembali ke Bab 4: Box Model & Spacing](./04-box-model.md)

</div>
<div align="right">

🔗 [Lanjut ke Bab 6 → Flexbox (Layout Modern)](./06-flexbox.md)

</div>
