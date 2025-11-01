# 🧩 BAB 2 — Selektor, Properti, dan Nilai

## 2.1 Jenis Selektor
| Jenis | Contoh | Menarget |
|-------|---------|----------|
| Tag | `p {}` | Semua `<p>` |
| Class | `.card {}` | Elemen dengan `class="card"` |
| ID | `#header {}` | Elemen dengan `id="header"` |
| Universal | `* {}` | Semua elemen |

> 💡 Gunakan **class** untuk styling umum, ID hanya untuk identitas unik (anchor atau JS).

---

## 2.2 Selektor Relasional
| Selektor | Contoh | Arti |
|-----------|---------|------|
| Descendant | `.card p` | Semua `<p>` di dalam `.card` |
| Child | `.card > p` | `<p>` anak langsung `.card` |
| Adjacent sibling | `h2 + p` | `<p>` langsung setelah `h2` |
| General sibling | `h2 ~ p` | Semua `<p>` setelah `h2` dalam satu parent |

---

## 2.3 Selektor Atribut
```css
a[target="_blank"] { text-decoration: underline; }
input[type="email"] { border-color: hsl(220 90% 56%); }
```

---

## 2.4 Pseudo-Class dan Pseudo-Element
```css
a:hover { opacity: .8; }
input:focus { outline: 2px solid hsl(220 90% 56%); }
li:first-child { font-weight: 600; }
p::first-line { text-transform: uppercase; }
```

---

## 2.5 Spesifisitas (Urutan Kekuatan)
Urutan menang (terkuat → terlemah):
1. Inline style  
2. `#id`  
3. `.class`, `[attr]`, `:pseudo-class`  
4. `tag`, `::pseudo-element`

> Hindari penggunaan `!important` berlebihan.

---

## 2.6 Contoh Properti Umum
### Warna & Teks
```css
body { color: #111; background: #fafafa; }
h1 { color: hsl(220, 90%, 56%); }
```

### Box Model
```css
.card {
  padding: 16px;
  margin: 16px 0;
  border: 1px solid #e5e7eb;
  border-radius: 8px;
}
```

### Display
| Properti | Nilai | Keterangan |
|-----------|--------|------------|
| `display` | `block`, `inline`, `inline-block`, `flex`, `grid` | Jenis tampilan |
| `visibility` | `visible`, `hidden` | Sembunyikan tanpa hilangkan ruang |
| `opacity` | `0–1` | Transparansi elemen |

---

## 2.7 Fungsi CSS Umum
```css
.box { width: min(90vw, 720px); }
.hero { padding: clamp(16px, 4vw, 48px); }
```
- `min()`, `max()`, `clamp()` membantu layout responsif tanpa media query.

---

## 2.8 Variabel CSS (Custom Properties)
```css
:root {
  --brand: hsl(220 88% 56%);
  --radius: 12px;
}
.btn {
  background: var(--brand);
  border-radius: var(--radius);
}
```

---

## 2.9 Contoh Selektor Terpadu
```html
<article class="post" id="artikel-utama">
  <h2 class="post__title">Judul Artikel</h2>
  <p class="post__meta">Ditulis oleh <a href="#">Alex</a></p>
  <p class="post__lead">Ini paragraf pembuka dengan <span class="tag">CSS</span>.</p>
  <a class="btn" href="#">Baca Selengkapnya</a>
</article>
```
```css
.post { border: 1px solid #e5e7eb; border-radius: 12px; padding: 20px; }
.post__title { margin: 0 0 8px; color: #111; }
.post__meta { color: #64748b; }
.post__meta a { color: hsl(220 88% 56%); text-decoration: none; }
.post__meta a:hover { text-decoration: underline; }
.btn { background: hsl(220 88% 56%); color: #fff; padding: 8px 16px; border-radius: 6px; }
```

---

## 2.10 Kesimpulan
- **Selector** menarget elemen  
- **Property** menentukan gaya  
- **Value** memberi hasil visual  
- Gunakan **class**, hindari `!important`, dan manfaatkan variabel CSS

---

<div align="left">

🔗 [← Kembali ke Bab 1: Pengenalan CSS](./01-pengenalan-css.md)

</div>
<div align="right">

🔗 [Lanjut ke Bab 3 → Warna, Teks, dan Font](./03-warna-teks-font.md)

</div>
