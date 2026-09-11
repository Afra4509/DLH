# 🌱 Platform Pengelolaan Sampah Terpadu

Platform penghubung **Warga ↔ RT/RW ↔ Pengelola Sampah ↔ DLH ↔ Partner/CSR**, yang mengubah kegiatan memilah dan menyetor sampah menjadi ekosistem bernilai — bagi warga (reward), RT/RW (pengelolaan wilayah), dan DLH (data & kebijakan).

> Inti sistem ini bukan sekadar aplikasi reward, melainkan **platform data dan monitoring pengelolaan sampah terpusat**. Reward hanyalah alat untuk mendorong partisipasi warga.

---

## 📋 Daftar Isi

- [Ringkasan Konsep](#ringkasan-konsep)
- [Alur Sistem](#alur-sistem)
- [Peran Pengguna](#peran-pengguna)
- [Fitur Utama](#fitur-utama)
- [Sistem Poin & Reward](#sistem-poin--reward)
- [Dashboard](#dashboard)
- [Alur Uang](#alur-uang)
- [Diagram Alur Besar](#diagram-alur-besar)

---

## Ringkasan Konsep

Sistem melibatkan tiga peran utama:

| Peran | Fungsi |
|---|---|
| **Warga** | Memilah & menyetor sampah, mengumpulkan poin, menukar reward |
| **RT/RW** | Memverifikasi warga & setoran sampah, mengelola data wilayah |
| **DLH** | Memonitor data agregat seluruh wilayah untuk evaluasi & kebijakan |

---

## Alur Sistem

### 1. Registrasi
- **Warga** mendaftar akun dengan data diri + RT/RW, akun otomatis terhubung ke wilayah.
- **RT/RW** mendaftar sebagai admin wilayah dan memverifikasi data warga yang masuk.

### 2. Warga Memilah Sampah
Kategori sampah yang didukung:
- ♻️ Plastik
- 📦 Kertas/Kardus
- 🥫 Logam
- 🍾 Kaca
- 🗑️ Residu

Website menampilkan jenis sampah yang bisa disetor beserta estimasi nilai/poinnya.

### 3. Warga Setor Sampah
Warga menekan **"Setor Sampah"** lalu mengisi:
- Jenis sampah
- Berat
- Waktu/lokasi setor

Sampah kemudian dibawa ke titik pengumpulan RT/RW.

### 4. Verifikasi RT/RW
Admin RT/RW menerima pengajuan (contoh: *Afra — Plastik — 3,5 kg*), menimbang, lalu:
- ✅ **Disetujui** → poin dihitung otomatis
- ❌ **Ditolak / berat dikoreksi** → jika tidak sesuai

---

## Sistem Poin & Reward

### Poin Warga
Contoh konversi: **1 kg plastik = 100 poin**

Warga dapat melihat ringkasan kontribusinya, misalnya:
```
Total Poin: 1.250
Sampah terkumpul: 12,5 kg
Kontribusi bulan ini: +350 poin
```
Unsur gamifikasi mendorong partisipasi aktif.

### Reward
Poin dapat ditukar dengan benefit berjenjang, misalnya:

| Poin | Reward |
|---|---|
| 500 | Voucher/benefit A |
| 1.000 | Benefit B |
| 2.000 | Benefit C |

⚠️ Reward **tidak muncul begitu saja** dari sistem — dananya berasal dari partner/CSR dan hasil penjualan sampah.

---

## Dashboard

### 🏘️ Dashboard RT/RW
Fitur utama bagi RT/RW untuk mengelola ekosistem wilayahnya:
- Data wilayah & jumlah warga terdaftar
- Jumlah warga aktif
- Total sampah terkumpul (per jenis)
- Total poin yang diberikan
- Progress bulanan

Contoh tampilan:
```
RT 05
👥 127 warga
♻️ 486 kg sampah terkumpul
📈 +18% dibanding bulan lalu
🏆 73 warga aktif
```

### 🏢 Dashboard DLH
Mengagregasi data dari seluruh RT/RW untuk kebutuhan monitoring & kebijakan:
- Total sampah terpilah per wilayah
- RT/RW dengan partisipasi tertinggi
- Jenis sampah paling banyak disetor
- Tren pemilahan sampah
- Wilayah dengan partisipasi rendah
- Estimasi sampah yang berhasil dialihkan dari pembuangan tercampur

```
RT 01 ─┐
RT 02 ─┤
RT 03 ─┼→ SISTEM → DASHBOARD DLH
RT 04 ─┤
RT 05 ─┘
```

---

## Alur Uang

Terdapat dua arus utama dalam sistem:

**Arus Sampah:**
```
Warga → RT/RW → Bank Sampah/Pengepul/Pengelola → Sampah Dijual → Pendapatan
```

**Arus Reward:**
```
Partner/CSR/Pendapatan Sampah → Dana Reward → Poin Warga → Benefit
```

---

## Diagram Alur Besar

```
                       WEBSITE
                          │
                ┌─────────┴─────────┐
                ↓                   ↓
             WARGA                RT/RW
                │                   │
          Registrasi          Verifikasi warga
                │                   │
          Pilah sampah              │
                │                   │
          Setor sampah ───────→ Timbang
                                    │
                                    ↓
                              Verifikasi data
                                    │
                                    ↓
                              Sistem hitung poin
                                    │
                       ┌────────────┴────────────┐
                       ↓                          ↓
                    WARGA                      DATABASE
                       │                          │
                 Tukar reward                     │
                                                   ↓
                                             DASHBOARD DLH
                                                   │
                                                   ↓
                                         Monitoring & evaluasi
```

**Alur bisnis:**
```
WARGA → Sampah terpilah → RT/RW → Bank Sampah/Pengelola → Pendapatan → Reward + Operasional

PARTNER/CSR → Dana program → Reward warga

RT/RW → Data terverifikasi → PLATFORM → DLH → Monitoring & kebijakan
```

---

## 🗂️ Struktur Prototype yang Disarankan

Untuk pengembangan prototype website, struktur menu dibagi menjadi **3 dashboard** dengan fitur berbeda:

1. **Dashboard Warga** — setor sampah, riwayat poin, tukar reward
2. **Dashboard RT/RW** — verifikasi setoran, data wilayah, progress bulanan
3. **Dashboard DLH** — monitoring agregat, tren, evaluasi kebijakan
