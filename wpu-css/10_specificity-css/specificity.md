Berikut ringkasan dari video tentang **CSS Specificity** dari channel *Web Programming Unpas*:

---

### 🎯 **Apa itu Specificity di CSS?**

Specificity adalah konsep dalam CSS yang menentukan *seberapa kuat* atau *spesifik* sebuah selektor CSS dalam memilih elemen HTML. Semakin spesifik selektor, semakin besar kemungkinan properti CSS-nya diterapkan pada elemen yang dimaksud.

---

### ⚖️ **Konsep Bobot (Weight) Selektor**

Selektor di CSS memiliki tingkat "berat" yang berbeda, yaitu:

* **Elemen HTML** (seperti `p`, `li`, `ul`): bobot **1**
* **Kelas** (`.nama-kelas`): bobot **10**
* **ID** (`#id-elemen`): bobot **100**
* **Inline style** (`style=""` di dalam tag HTML): bobot **1000** (paling kuat)

---

### 🔢 **Cara Menghitung Specificity**

Bayangkan seperti 4 digit angka:
**\[inline] \[ID] \[class] \[elemen]**

Contoh:
* `p` → 0001
* `.favorit` → 0010
* `#p1` → 0100
* `style="color:red"` → 1000
---

### 🧪 **Contoh Kasus**

1. **Dua Selektor Sama**:

   ```CSS
   p { color: red; }
   p { color: green; }
   ```

   → Hasil: Warna **hijau**, karena aturan terakhir yang ditulis akan menang kalau spesifikasinya sama.

2. **ID vs Elemen**:

   ```CSS
   #p1 { color: red; }
   p { color: green; }
   ```

   → Hasil: Warna **merah**, karena `#p1` (0100) lebih berat daripada `p` (0001).

3. **Kelas vs Selektor Kombinasi**:
   HTML:

   ```HTML
   <ul id="sarapan">
     <li class="favorit">Nasi Goreng</li>
   </ul>
   ```

   CSS:

   ```CSS
   ul#sarapan li { color: green; }
   .favorit { color: red; }
   ```

   → Hasil: Warna **hijau**, karena `ul#sarapan li` = 0102 > `.favorit` = 0010.

   Solusi:
   Tambah beban di `.favorit` supaya lebih spesifik:

   ```CSS
   <style>
   ul#sarapan .favorit { color: red; }
   </style>
   ```

---

### 🛠 **Tips Tambahan**

* Gunakan [Specificity Calculator](https://specificity.keegan.st/) untuk membantu menghitung dan membandingkan selektor.
* Hindari terlalu banyak menggunakan `inline-style`, karena sulit dikelola.
* Ketika menggabungkan CSS buatan sendiri dengan CSS orang lain, pastikan selektor kamu cukup spesifik untuk mengoverride style yang ada.

---

Kalau kamu mau, aku juga bisa buatin versi infografis atau mindmap dari materi ini. Mau? 😊
