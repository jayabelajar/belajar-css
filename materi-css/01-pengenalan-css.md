# 🎨 BAB 1 — Pengenalan CSS & Cara Kerja

## 1.1 Apa itu CSS?
**CSS (Cascading Style Sheets)** adalah bahasa untuk mengatur tampilan (presentasi) dokumen HTML:
- Mengatur **warna, font, ukuran**, jarak, tata letak, dan responsivitas.
- Memisahkan **struktur (HTML)** dan **gaya (CSS)** agar kode rapi & mudah dipelihara.

> 🔑 *Cascading* berarti aturan yang “mengalir” dan dapat saling menimpa sesuai **urutan, spesifisitas,** dan **inheritance**.

---

## 1.2 Cara Menyematkan CSS
### 1️⃣ External (Direkomendasikan)
```html
<link rel="stylesheet" href="assets/css/style.css">
```
Kelebihan: terstruktur, *cacheable*, mudah dipelihara untuk banyak halaman.

### 2️⃣ Internal (di `<style>` dalam `<head>`)
```html
<style>
  body { font-family: system-ui; margin: 0; }
</style>
```
Cocok untuk halaman tunggal atau prototipe kecil.

### 3️⃣ Inline (dalam atribut `style`)
```html
<h1 style="color:#2563eb; margin:0;">Halo CSS</h1>
```
Cepat, tapi **tidak disarankan** untuk proyek besar karena sulit dikelola.

---

## 1.3 Sintaks Dasar CSS
```css
/* selector */        /* deklarasi */
p {                    /* blok aturan */
  color: #111;         /* properti: nilai; */
  line-height: 1.6;
}
```
- **Selector**: elemen yang ditarget (`p`, `.btn`, `#header`)
- **Property**: gaya yang ingin diatur (`color`, `margin`)
- **Value**: nilainya (`#111`, `16px`, `1.6`)

---

## 1.4 Jenis Satuan Umum
| Jenis | Satuan | Keterangan |
|-------|--------|------------|
| Absolut | `px` | Ukuran pasti |
| Relatif | `em`, `rem` | Berdasarkan font induk |
| Persen | `%` | Relatif terhadap elemen induk |
| Viewport | `vw`, `vh` | Relatif terhadap layar |
| Warna | `#hex`, `rgb()`, `hsl()` | Format warna |

Contoh:
```css
h1 { color: hsl(220, 90%, 56%); } /* Biru */
```

---

## 1.5 Box Model (Gambaran Awal)
Semua elemen di HTML memiliki 4 lapisan: **content → padding → border → margin**
```css
.card {
  box-sizing: border-box;
  width: 300px;
  padding: 16px;
  border: 1px solid #e5e7eb;
  margin: 16px auto;
}
```
> 💡 `box-sizing: border-box` membuat padding dan border dihitung dalam total lebar elemen.

---

## 1.6 Prioritas (Cascade) & Spesifisitas
Urutan prioritas gaya:
1. Inline style
2. `#id`
3. `.class` atau pseudo-class
4. Tag elemen (`p`, `div`, `h1`)
5. Urutan terakhir dalam file

> Gunakan `.class` untuk styling agar tetap fleksibel.

---

## 1.7 Contoh Mini Project
**index.html**
```html
<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width,initial-scale=1">
  <title>Belajar CSS3</title>
  <link rel="stylesheet" href="assets/css/style.css">
</head>
<body>
  <header class="site-header">
    <h1>Belajar CSS3</h1>
    <p class="tagline">Styling modern & rapi</p>
  </header>

  <main class="container">
    <article class="card">
      <h2>Pengenalan</h2>
      <p>CSS memisahkan tampilan dari struktur sehingga kode lebih bersih.</p>
      <a class="btn" href="#">Mulai</a>
    </article>
  </main>
</body>
</html>
```

**assets/css/style.css**
```css
* { box-sizing: border-box; }

:root {
  --brand: hsl(220, 88%, 56%);
  --text: #111;
  --muted: #6b7280;
  --bg: #fafafa;
}

body {
  font-family: system-ui, sans-serif;
  color: var(--text);
  background: var(--bg);
  margin: 0;
}

.site-header {
  text-align: center;
  padding: 32px 16px;
}
.site-header h1 { color: var(--brand); margin: 0; }
.site-header .tagline { color: var(--muted); }

.container { max-width: 720px; margin: 24px auto; padding: 0 16px; }

.card {
  background: #fff;
  padding: 20px;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
}
.card h2 { margin-top: 0; }

.btn {
  display: inline-block;
  margin-top: 8px;
  padding: 10px 16px;
  background: var(--brand);
  color: #fff;
  border-radius: 6px;
  text-decoration: none;
}
.btn:hover { filter: brightness(1.05); }
```

---

## 1.8 Best Practice
- Gunakan **CSS eksternal**
- Terapkan `box-sizing: border-box`
- Gunakan variabel untuk warna/spacing
- Hindari `!important` dan inline style
- Gunakan **validator CSS W3C**

---

<div align="left">

🔗 [← Kembali ke README](../README.md)

</div>
<div align="right">

🔗 [Lanjut ke Bab 2 → Selektor, Properti, dan Nilai](./02-selektor-properti-nilai.md)

</div>
