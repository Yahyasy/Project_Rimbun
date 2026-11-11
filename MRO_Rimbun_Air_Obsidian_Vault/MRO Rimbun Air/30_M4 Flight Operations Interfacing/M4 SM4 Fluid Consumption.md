---
tipe: submodul
modul: M4
diperbarui: 2026-11-11
sumber:
  - claude/Keputusan_Fluid_Consumption_Modul4_4Nov.md
  - claude/Konfirmasi_Modul4_5Nov.md
tags: [m4]
aliases: [Fluid Consumption, Oil Consumption, Fuel Uplift, Hydraulic]
---
# M4 SM4 Fluid Consumption

> [!important] Struktur baru 4 Nov (FL-01) menggantikan Flow Detail 3 Nov
> Menu lama 4.1 Oil Uplift, 4.2 Fuel Record, 4.3 Fuel Drain Check, 4.4 Oil Consumption Report, 4.5 Fuel Report **tidak berlaku**. Oil Consumption hanya di menu 4.2; tab Oil Consumption di Reliability Report dihapus (FL-03).

Semua fluid **diinput di AFML, Tab Oil & Fuel**. Ketiga menu hanya daftar dan hitungan tanpa form input; yang tampil hanya halaman **Closed** (Void dilewati) (FL-02).

## Menu

| Menu | Isi | Status | Acuan |
|---|---|---|---|
| **4.1 Fuel Uplift** | Kolom: tanggal, No. AFML/sektor, rute, remaining, uplift, total/onboard, fuel burn (B737) atau fuel used Eng 1 & Eng 2 (ATR), sisa akhir (B737), receipt no. Tanpa hitungan per baris; total uplift & burn per registrasi per periode. Uplift **liter**; remaining/total/burn **KG atau LBS** sesuai tipe. Remaining tidak divalidasi (bacaan pilot) | Layar baru dari template list | FL-05 |
| **4.2 Oil Consumption** | Kolom: No. AFML per sektor, Eng 1 top-up & QT/FH, Eng 2 top-up & QT/FH, lalu top-up posisi lain per tipe (B737: IDG 1, IDG 2, APU; ATR: Others) | Pindah dari tab 5.1 | FL-03, FL-04 |
| **4.3 Hydraulic Fluid Consumption** | Salinan 4.2 dengan kolom hydraulic; ATR per sistem **Blue** dan **Green**; B737 satu nilai HYD FLD added; Others tanpa QT/FH | Salinan 4.2 | FU-01 → K5-05 |

## Rumus

| Hitungan | Rumus | Status | Acuan |
|---|---|---|---|
| **QT/FH oli per engine** | Oli yang ditambahkan ÷ total FH sejak top-up sebelumnya engine itu, **sampai dan termasuk** sektor top-up; nilai bertahan sampai top-up berikutnya | Final | FL-04, REL-18, WB-07, WB-08 |
| Contoh papan tulis | 1 QT ÷ 4:00 = 0,25; 2 QT ÷ 4:00 = 0,5 | — | WB |
| Oli non-engine | IDG, APU, Others dicatat **tanpa** QT/FH | Final | FL-04 |
| **QT/FH hydraulic** | Sama dengan oli, basis **FH** per sistem; basis per cycle tidak dipakai saat ini | Final (5 Nov) | K5-05 |
| Contoh ATR | Green 0,4 QT, jendela 4:00 = 0,10; Blue 0,3 QT, jendela 6:00 = 0,05 | — | FU-01 |
| Hitung ulang | Bila jam sektor dikoreksi lewat Correct Flight Log | Final | LM-11 |

## Aturan pencatatan

- Oli engine per engine per sektor dalam QT, qty desimal; kaleng yang dibuka selalu habis, tidak ada oli yang dikembalikan.
- PN oli/hydraulic hanya dari yang **di-issue ke WO** pesawat tersebut; registrasi dibaca otomatis dari WO; satuan mengikuti PN dan tidak bisa diubah (K5-09).
- Pemakaian oli **tidak** dikirim balik ke Modul 5; saldo oli per registrasi tidak dimasukkan ke menu (AF-05, FU-02).
- Tab Engine Parameter disertakan di AFML (AF-07), bukan di sub-modul ini.

## Ditahan

| Kode | Butir | Selama ditahan |
|---|---|---|
| WQ-04 | Batas QT/FH per tipe engine & per sistem hydraulic untuk warna peringatan | Angka tampil tanpa warna |
| WQ-03, WQ-06 | Oli dicatat sesudah sektor mendarat; aturan ATR sama dengan B737 | Dipakai sebagai asumsi |

Fuel Drain Check tidak dibuat (checklist pre-flight, transit, daily tetap di kertas; Q26-13); oli APU (Q28-07) mengikuti posisi APU B737.
