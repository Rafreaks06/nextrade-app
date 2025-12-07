# 🌍 NEXTRADE — AI Export Intelligence Platform

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **“Membantu UMKM Indonesia menembus pasar ekspor hanya dengan satu klik.”**

NexTrade adalah platform **AI Export Intelligence** yang dirancang untuk memberdayakan Usaha Mikro, Kecil, dan Menengah (UMKM) Indonesia. Kami menggabungkan data perdagangan global dari **UN Comtrade**, regulasi **WTO**, dan kemampuan **Generative AI** untuk menyajikan peluang ekspor yang cepat, akurat, dan mudah dipahami.

Cukup masukkan nama produk Anda, dan NexTrade akan memberikan analisis lengkap, mulai dari negara target yang cocok, potensi profit, harga global, risiko regulasi, hingga membuat **email penawaran profesional** secara instan.

---

## 🚀 Mengapa NexTrade Penting?

Banyak UMKM Indonesia yang gagal menembus pasar global karena hambatan informasi:

* ❌ **Ketidakpastian Pasar:** Tidak tahu negara mana yang memiliki *demand* (permintaan) tinggi.
* ❌ **Regulasi & Kode:** Kesulitan memahami **HS Code** dan aturan ekspor–impor.
* ❌ **Data Harga:** Tidak punya akses data harga kompetitif di pasar global.
* ❌ **Komunikasi:** Tidak percaya diri dalam menyusun email penawaran ke *buyer* luar negeri.

**NexTrade mengatasi semua tantangan ini dalam satu platform yang terintegrasi.**

---

## ✨ Fitur Utama

### 1. 🧠 AI Product Understanding
Ketik nama produk apapun (misalnya: "rotan mentah", "cabai merah", "batu bara"), dan AI akan segera:
* ✔ Mengidentifikasi **HS Code** yang relevan.
* ✔ Menentukan kategori dan konteks industri produk ekspor.

### 2. 🗺️ Smart Market Finder
Analisis data impor dari 200+ negara menggunakan UN Comtrade untuk menemukan target pasar terbaik:
* ✔ Negara dengan **demand tertinggi** dan potensi pertumbuhan.
* ✔ Volume impor, tren historis, dan industri pengguna produk tersebut.

### 3. 💸 Profit Calculator (Mode Kalkulasi)
Bandingkan harga jual Anda dengan harga pasar global (USD) secara *real-time*:
* ✔ Indikator profit: **HIGH PROFIT / MODERATE / LOSS**.
* ✔ Perhitungan margin otomatis (FOB/CIF).
* ✔ Visualisasi jalur ekspor (Arc Map) yang interaktif.

### 4. 📜 WTO Regulation Check
Cek regulasi impor negara tujuan untuk memitigasi risiko:
* ✔ Larangan impor yang berlaku.
* ✔ Persyaratan **SPS** (Sanitary and Phytosanitary) & **TBT** (Technical Barriers to Trade).
* ✔ Informasi mengenai *Restrictions* dan *Quota*.

### 5. 💡 AI Market Insight
Hasil analisis disajikan dalam kartu ringkas untuk pemahaman instan:
* **Market Demand:** Seberapa besar peluang di negara target.
* **Price Target:** Rekomendasi harga jual global.
* **Regulatory Check:** Status kepatuhan regulasi.
* **Verdict & Recommendation:** Kesimpulan dan langkah selanjutnya yang harus diambil.

### 6. 📧 Auto-Generated Export Email
Hanya dalam 3 detik, NexTrade menghasilkan **email penawaran profesional** yang siap dikirim:
* ✔ Disusun dalam Bahasa Inggris bisnis yang formal.
* ✔ Berisi ringkasan harga, volume, dan keunggulan produk.
* ✔ **Tinggal *copy–paste*** ke calon *buyer* atau ITPC.

---

## 🧱 Tech Stack

| Kategori | Teknologi | Deskripsi |
| :--- | :--- | :--- |
| **Frontend** | Next.js 14 (App Router) | Kerangka kerja React untuk performa tinggi. |
| | TailwindCSS | Utilitas CSS untuk desain responsif dan cepat. |
| | Framer Motion | Library untuk animasi dan interaksi yang mulus. |
| | Deck.gl (ArcLayer) & MapLibre GL | Visualisasi data geo-spasial dan pemetaan interaktif. |
| **Backend** | FastAPI (Python) | API modern, cepat, dan berperforma tinggi. |
| | UN Comtrade API | Sumber data perdagangan impor/ekspor global. |
| | WTO / ePing Scraper | Mengambil data regulasi teknis dan non-teknis. |
| | HuggingFace Transformers / LLM | Engine AI Generatif untuk *insight* dan pembuatan email. |
| | Custom Simulation Engine | Mekanisme *fallback* saat batas API Comtrade tercapai. |

---

## 📦 Struktur Folder Proyek

### 🖥️ Frontend (Next.js)
```

frontend/
├── app/
│   ├── analyze/           ← Halaman hasil analisis
│   ├── page.jsx            ← Halaman utama (landing page)
│
├── components/
│   ├── analyze/           ← Komponen khusus halaman analisis
│   ├── faq/                ← FAQ
│   ├── hero/               ← Bagian utama (Hero)
│   ├── showcase/           ← Demo fitur
│
├── public/
│   ├── demo.png            ← Screenshot demo
│   ├── logo.svg

```

### 🐍 Backend (FastAPI)
```

backend/
├── ai\_engine.py            ← Logika inti AI (insight & email generation)
├── main.py                 ← Entry point server FastAPI
├── utils.py                ← Helper functions
├── WtoQrlst.py             ← Modul scraping data WTO
├── wtoSearcheping.py       ← Parser data ePing
├── data/                   ← Dataset lokal
├── requirements.txt

````

---

## 🔧 Cara Instalasi & Menjalankan Proyek (Integrated)

Pastikan Anda telah menginstal **Python 3.10+** (untuk *backend*) dan **Node.js 18+** (untuk *frontend*).

### A. Persiapan Backend (FastAPI)

1.  **Arahkan ke Direktori Backend:**
    ```bash
    cd backend-export-intel
    ```

2.  **Instal Dependensi Python:**
    ```bash
    pip install -r requirements.txt
    ```

3.  **Konfigurasi Environment:**
    Buat file `.env` di direktori `backend-export-intel/` dan isi dengan kunci API Anda:
    ```
    KOLOSAL_API_KEY=...
    COMTRADE_KEY=...
    WTO_API_KEY=...
    ```

4.  **Jalankan Server Backend:**
    ```bash
    python main.py
    ```
    Backend akan berjalan dan siap menerima permintaan di **[http://localhost:8000](http://localhost:8000)**.

### B. Persiapan Frontend (Next.js)

1.  **Pindah Direktori ke Frontend:**
    ```bash
    # Kembali ke root project, lalu masuk ke direktori frontend
    cd ../nextrade-hackaton
    ```

2.  **Instal Dependensi Node.js:**
    ```bash
    npm install
    ```

3.  **Jalankan Aplikasi Frontend:**
    ```bash
    npm run dev
    ```
    Frontend akan tersedia di browser Anda di **[http://localhost:3000](http://localhost:3000)**.

> ℹ️ **Catatan:** Pastikan server backend (`localhost:8000`) sudah berjalan sebelum Anda mencoba mengakses fitur utama di frontend (`localhost:3000`), karena frontend bergantung pada API untuk mendapatkan data analisis.

---

## 🛡️ Keamanan & Kestabilan

Kami membangun sistem ini dengan memprioritaskan stabilitas data:

* ✔ **Fallback Logic:** Jika API UN Comtrade mencapai batas *rate limit*, sistem secara otomatis beralih menggunakan *Custom Simulation Engine* internal.
* ✔ **Error-Handling:** Penanganan respons data WTO/ePing yang sering tidak konsisten (JSON/HTML).
* ✔ **Rate-Limit Prevention:** Implementasi *batching* untuk mengurangi permintaan *real-time* ke LLM/AI.
* ✔ **Deployment:** Arsitektur yang siap untuk deployment dengan HTTPS.

---

## 🏆 Mengapa NexTrade Layak Menang?

NexTrade bukan hanya *proof-of-concept*, tapi solusi yang **berfungsi penuh** dan **dapat ditindaklanjuti (actionable)**:

1.  **Relevansi Sosial:** Memberikan solusi nyata terhadap masalah esensial yang dihadapi UMKM Indonesia dalam mencapai pasar global.
2.  **Integrasi Data Kompleks:** Berhasil mengintegrasikan 3 sumber data utama yang berbeda (AI, Data Perdagangan, Regulasi WTO) menjadi satu alur kerja yang mulus.
3.  **User Experience (UX):** Tampilan modern, interaktif, dan hasil yang disajikan dalam format kartu ringkas, membuatnya sangat mudah dipahami oleh pengguna awam sekalipun.
4.  **Actionable Output:** Menghasilkan output yang langsung bisa digunakan (email penawaran) untuk *pitching* ke ITPC atau calon *buyer*.
````
