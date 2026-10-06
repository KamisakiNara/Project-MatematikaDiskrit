# LogicLab - Pemeriksa Proposisi

Project 3 Hari Matematika Diskrit, Program Studi Ilmu Komputer (UNIMED)
Dosen: Nurul Maulida Surbakti, M.Si.
Kelompok: 1
Anggota:
- Muhammad Kahfi	4253250020
- Muhammad Raihan Syahfitrah	4253250032
- Muhammad Zidane Ariefani	4253250048
- Siti Syafa Marwa	4251250017

Website sederhana untuk membuat **tabel kebenaran** dan menentukan sebuah ekspresi logika termasuk **tautologi**, **kontradiksi**, atau **kontingensi**.

## Fitur

- Tabel kebenaran lengkap dengan kolom sub-ekspresi (langkah evaluasi terlihat).
- Klasifikasi otomatis: tautologi, kontradiksi, kontingensi.
- **Mode Detektif**: menampilkan baris saksi bernilai T dan F sebagai bukti klasifikasi.
- **Validasi manual per baris**: klik baris tabel untuk melihat perhitungan substitusi nilai.
- **Uji Ekuivalensi**: membandingkan dua ekspresi (misalnya hukum De Morgan).

## Cara Menjalankan

1. Buka folder project, lalu cari file `logiclab.html`.
2. Klik dua kali file tersebut agar terbuka di browser (Chrome, Edge, Firefox, atau Safari).
3. Selesai. Tidak perlu instalasi, server, atau koneksi internet.

## Kebutuhan Library

Tidak ada. Program ditulis dengan HTML, CSS, dan JavaScript murni dalam satu file, tanpa library eksternal, database, atau backend.

## Aturan Penulisan Ekspresi

| Operator | Simbol | Alternatif ketikan |
|---|---|---|
| Negasi (not) | ¬ | `~` atau `!` |
| Konjungsi (and) | ∧ | `&` atau `^` |
| Disjungsi (or) | ∨ | `\|` atau huruf `v` |
| Implikasi | → | `->` |
| Bikonditional | ↔ | `<->` |
| Xor | ⊕ | - |

- Variabel berupa huruf (P, Q, R, dan seterusnya), maksimal 5 variabel. Huruf `v` tidak dapat dipakai sebagai variabel karena dibaca sebagai "atau".
- Prioritas operator: ¬ > ∧ > ∨ dan ⊕ > → > ↔. Gunakan tanda kurung untuk memperjelas.

## Contoh Input

**Tab "Periksa Ekspresi"**

| No | Input | Hasil yang diharapkan |
|---|---|---|
| 1 | `P ∨ ¬P` | Tautologi |
| 2 | `P ∧ ¬P` | Kontradiksi |
| 3 | `(P → Q) ∧ P` | Kontingensi |
| 4 | `(P → Q) ↔ (¬Q → ¬P)` | Tautologi (kontraposisi) |

**Tab "Uji Ekuivalensi"**

| No | Ekspresi 1 | Ekspresi 2 | Hasil yang diharapkan |
|---|---|---|---|
| 1 | `P → Q` | `¬P ∨ Q` | Ekuivalen |
| 2 | `¬(P ∧ Q)` | `¬P ∨ ¬Q` | Ekuivalen (De Morgan) |
| 3 | `P → Q` | `Q → P` | Tidak ekuivalen |

## Cara Kerja Singkat

1. **Tokenisasi**: teks ekspresi dipecah menjadi token (variabel, operator, kurung).
2. **Parsing**: token disusun menjadi pohon ekspresi sesuai prioritas operator.
3. **Evaluasi**: ekspresi dihitung untuk seluruh 2ⁿ kombinasi nilai variabel.
4. **Klasifikasi**: semua T → tautologi, semua F → kontradiksi, selain itu → kontingensi.

## Keterbatasan

- Maksimal 5 variabel (32 baris).
- Hanya mendukung operator ¬, ∧, ∨, ⊕, →, ↔ (tanpa kuantor).
- Tidak ada fitur penyederhanaan ekspresi.
