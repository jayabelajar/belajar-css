# 🧪 BAB 11 — CSS Variables (Custom Properties)

## 11.1 Apa itu CSS Variables?
**CSS Variables (Custom Properties)** adalah variabel yang disimpan di CSS menggunakan sintaks `--nama-var` dan dipanggil dengan `var(--nama-var)`. Keunggulan:
- Konsistensi gaya (warna, spacing, radius).
- Mudah *theming* (light/dark).
- Dapat diwariskan (inherit) dan di-*override* per-komponen.

---

## 11.2 Dasar Penggunaan
```css
:root {
  --brand: hsl(220, 83%, 57%);
  --text: #0f172a;
  --radius: 10px;
  --space: 16px;
}

.button {
  background: var(--brand);
  color: #fff;
  border-radius: var(--radius);
  padding: calc(var(--space) * .75) var(--space);
}
```
> `:root` menaruh variabel di scope global (dokumen).

---

## 11.3 Scope, Inheritance, & Override
```css
:root { --brand: hsl(220 83% 57%); }

.card { --brand: hsl(14 90% 60%); } /* override di dalam .card */

.card .btn {
  background: var(--brand); /* pakai versi card */
}
```
- Variabel **mewarisi** nilai dari parent.
- Bisa di-*override* di level komponen/container.

---

## 11.4 Fallback (Nilai Cadangan)
```css
.title {
  color: var(--heading, #111); /* #111 dipakai jika --heading belum didefinisikan */
}
```

---

## 11.5 Variabel + Fungsi `calc()`, `min()`, `max()`, `clamp()`
```css
:root {
  --gutter: 16px;
  --max-content: 720px;
}
.container {
  padding-inline: var(--gutter);
  width: min(100%, var(--max-content));
}
.hero-title {
  font-size: clamp(1.5rem, 4vw, 2.5rem);
}
```

---

## 11.6 Theming (Light/Dark) dengan Media Query
```css
:root {
  --bg: #ffffff;
  --text: #0f172a;
}
@media (prefers-color-scheme: dark) {
  :root {
    --bg: #0f172a;
    --text: #f1f5f9;
  }
}
body { background: var(--bg); color: var(--text); }
```

---

## 11.7 Theming Per-Komponen (Stateful)
```css
.card { --surface: #fff; --ring: hsl(220 88% 70% / .35); }
.card {
  background: var(--surface);
  box-shadow: 0 0 0 0 transparent;
  transition: box-shadow .2s ease;
}
.card:hover { box-shadow: 0 0 0 4px var(--ring); }
```

---

## 11.8 Variabel Dinamis via Kustom Properti Inline
> Cocok untuk data-driven style (misal progress).
```html
<div class="progress" style="--value: 62%"></div>
```
```css
.progress {
  width: 240px; height: 10px; background: #e5e7eb; border-radius: 999px;
  position: relative; overflow: hidden;
}
.progress::before {
  content: "";
  position: absolute; inset: 0;
  width: var(--value, 0%); /* fallback 0% */
  background: hsl(220 83% 57%);
}
```

---

## 11.9 Interop dengan JavaScript (Opsional)
```js
// set
document.documentElement.style.setProperty('--brand', 'hsl(280 80% 60%)');
// get
const brand = getComputedStyle(document.documentElement).getPropertyValue('--brand');
```

---

## 11.10 Anti-Pattern & Tips
- ❌ Menaruh semua variabel di satu file tanpa logika → **kelola per domain** (color, spacing, radius).
- ❌ Nama variabel generic (`--blue`, `--grey`) → **gunakan semantik** (`--brand`, `--surface`, `--muted`).
- ✅ Pakai `:root` untuk default, override di komponen untuk tema lokal.
- ✅ Kombinasikan dengan `@media` / `@supports` saat perlu.

---

<div align="left">

🔗 [← Kembali ke Bab 10: Responsive Design & Media Query](./10-responsive-mediaquery.md)

</div>
<div align="right">

🔗 [Lanjut ke Bab 12 → Praktik Terbaik & Struktur CSS](./12-praktik-terbaik.md)

</div>
