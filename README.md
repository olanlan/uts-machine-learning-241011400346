# UTS Machine Learning

**Nama  :** Olan Lastiant Afri
**NIM   :** 241011400346
**Kelas :** Reg C
**random_state :** 46

## Ringkasan Hasil

### Bagian A: Linear Regression (Ads_Data.csv)

Split 80:20 (32 data train, 8 data test).

- Persamaan regresi: ŷ = 28.4656 + 9.0222 X
- Setiap kenaikan biaya iklan 1 juta Rp, penjualan naik rata-rata sekitar 9.02 juta Rp.

| Data | MAE | MSE | RMSE | R² |
|---|---|---|---|---|
| Train | 4.983 | 41.861 | 6.470 | 0.9232 |
| Test | 2.790 | 13.198 | 3.633 | 0.9863 |

Eksperimen gradient descent (5000 iterasi):

| Learning rate | Intercept | Koefisien | Keterangan |
|---|---|---|---|
| 0.001 | 17.759 | 10.704 | Terlalu lambat |
| 0.02 | 28.466 | 9.022 | Pas, sama dengan normal equation |
| 0.1 | nan | nan | Divergen (overflow) |

Prediksi penjualan: biaya iklan 4.5 juta = 69.07 juta, 7 juta = 91.62 juta, 12 juta = 136.73 juta (ekstrapolasi, kurang bisa dipercaya).

### Bagian B: Logistic Regression (Email_Data.csv)

Split 75:25 (45 data train, 15 data test), learning rate 0.1, 10000 iterasi.

- Persamaan: P(Spam) = σ(−10.408 + 0.867 · JumlahLink + 0.894 · KataPromo)
- Decision boundary: x₂ = 11.637 − 0.969 · x₁

| Threshold | Accuracy | Precision | Recall | FP | FN |
|---|---|---|---|---|---|
| 0.3 | 0.733 | 0.750 | 0.750 | 2 | 2 |
| 0.5 | 0.800 | 0.857 | 0.750 | 1 | 2 |
| 0.7 | 0.867 | 1.000 | 0.750 | 0 | 2 |