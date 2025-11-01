# ⚡ BAB 9 — Transition & Animation

## 9.1 Transition: Efek Halus Antar Keadaan
**Transition** membuat perubahan CSS menjadi halus (smooth), bukan instan.

```css
.box {
  background: hsl(220,83%,57%);
  width: 120px;
  height: 120px;
  transition: all 0.3s ease;
}
.box:hover {
  background: hsl(14,90%,60%);
  transform: scale(1.1);
}
```

| Properti | Fungsi | Contoh |
|-----------|---------|--------|
| `transition-property` | Properti yang diubah | `color`, `transform` |
| `transition-duration` | Durasi | `0.5s`, `300ms` |
| `transition-timing-function` | Kurva percepatan | `ease`, `linear`, `ease-in`, `ease-out` |
| `transition-delay` | Jeda sebelum mulai | `0.2s` |

> 💡 Gunakan `transition: all 0.3s ease;` untuk transisi global cepat.

---

## 9.2 Contoh Button dengan Transition
```css
.btn {
  background: hsl(220,83%,57%);
  color: #fff;
  padding: 12px 20px;
  border-radius: 6px;
  transition: background 0.3s ease, transform 0.2s;
}
.btn:hover {
  background: hsl(14,90%,60%);
  transform: translateY(-2px);
}
```

---

## 9.3 Animation: Gerakan Berulang
**Animation** digunakan untuk membuat elemen bergerak atau berubah terus-menerus.

```css
@keyframes slide {
  from { transform: translateX(0); }
  to { transform: translateX(100px); }
}

.box {
  animation: slide 2s ease-in-out infinite alternate;
}
```

| Properti | Fungsi |
|-----------|--------|
| `animation-name` | Nama keyframe |
| `animation-duration` | Lama animasi |
| `animation-timing-function` | Pola gerak |
| `animation-delay` | Jeda sebelum mulai |
| `animation-iteration-count` | Jumlah pengulangan (`infinite`) |
| `animation-direction` | `normal`, `reverse`, `alternate` |

---

## 9.4 Contoh Loading Spinner
```html
<div class="spinner"></div>
```
```css
.spinner {
  width: 40px;
  height: 40px;
  border: 4px solid #e5e7eb;
  border-top-color: hsl(220,83%,57%);
  border-radius: 50%;
  animation: spin 1s linear infinite;
}

@keyframes spin {
  to { transform: rotate(360deg); }
}
```

---

## 9.5 Fade-In Effect
```css
.fade-in {
  opacity: 0;
  animation: fade 1s ease forwards;
}
@keyframes fade {
  to { opacity: 1; }
}
```

---

## 9.6 Text Animation
```css
@keyframes typing {
  from { width: 0; }
  to { width: 100%; }
}
.typing {
  width: 0;
  white-space: nowrap;
  overflow: hidden;
  border-right: 2px solid;
  animation: typing 3s steps(30) forwards;
}
```

---

## 9.7 Tips Efek Transisi
- Gunakan transisi maksimal 0.5s agar terasa alami.  
- Hindari animasi berat di elemen besar (gunakan `will-change`).  
- Gunakan `prefers-reduced-motion` untuk aksesibilitas.  
- Animasi sebaiknya mendukung fungsi, bukan sekadar gaya.

---

<div align="left">

🔗 [← Kembali ke Bab 8: Background & Gradien](./08-background-gradien.md)

</div>
<div align="right">

🔗 [Lanjut ke Bab 10 → Responsive Design & Media Query](./10-responsive-mediaquery.md)

</div>
