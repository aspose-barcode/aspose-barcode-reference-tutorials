---
category: general
date: 2026-10-28
description: Pelajari cara membuat extended codetext di Python menggunakan ExtCodetextBuilder.
  Termasuk data plain dan data yang dienkode ECI, kode langkah demi langkah, serta
  tips praktik terbaik.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: id
lastmod: 2026-10-28
og_description: Buat teks kode yang diperluas di Python dengan ExtCodetextBuilder.
  Tutorial ini menunjukkan penanganan data biasa dan data yang dienkode ECI, kode
  lengkap yang dapat dijalankan, serta jebakan umum.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Buat teks kode yang diperluas di Python – panduan lengkap
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: Cara membuat codetext yang diperluas di Python dengan ExtCodetextBuilder
url: /id/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara membuat extended codetext di Python dengan ExtCodetextBuilder

Jika Anda perlu **membuat extended codetext** untuk aplikasi barcode atau data‑matrix, panduan ini menunjukkan secara tepat cara melakukannya di Python. Anda akan melihat cara menggabungkan plain text, menambahkan bagian ECI (Extended Channel Interpretation) untuk karakter Unicode, dan mengambil satu string yang diformat dengan benar siap untuk encoding.

Tutorial ini mencakup semua hal mulai dari menginstal library yang diperlukan hingga menangani kasus tepi seperti nilai ECI yang tidak didukung. Pada akhir tutorial Anda akan memiliki pola yang dapat digunakan kembali yang dapat Anda masukkan ke dalam proyek apa pun yang perlu **membuat extended codetext**.

## Apa yang akan Anda pelajari

* Peran `ExtCodetextBuilder` saat membangun string mixed‑encoding.  
* Cara **menambahkan plain codetext** dan **menambahkan ECI codetext** dalam satu instance builder.  
* Cara memverifikasi output akhir dan memecahkan masalah umum.  
* Variasi untuk set karakter lain (mis., ISO‑8859‑1, Shift‑JIS).  

### Prasyarat

* Python 3.8 atau lebih baru.  
* Package `extcodetext` (atau library serupa yang menyediakan `ExtCodetextBuilder`). Instal dengan:

```bash
pip install extcodetext
```

* Pemahaman dasar tentang Unicode dan nilai ECI – ECI 3 sesuai dengan UTF‑8, ECI 4 ke ISO‑8859‑1, dll.

> **Pro tip:** Simpan tabel referensi nomor ECI yang mudah diakses. Ini mencegah ketidaksesuaian tidak sengaja antara encoding yang dinyatakan dan urutan byte sebenarnya.

## Memahami ExtCodetextBuilder

`ExtCodetextBuilder` adalah utilitas kecil yang menggabungkan beberapa fragmen teks sambil secara otomatis menyisipkan penanda ECI yang diperlukan. Penanda ECI memberi tahu encoder barcode hilir mana set karakter yang harus digunakan untuk byte berikutnya. Tanpa penanda tersebut, karakter non‑ASCII akan ditafsirkan secara salah.

Builder bekerja dalam tiga fase sederhana:

1. **Membuat** instance builder.  
2. **Menambahkan** fragmen plain atau ECI‑encoded.  
3. **Mengambil** string extended‑codetext yang digabungkan.

Di bawah ini kami menjelaskan setiap fase dengan kode konkret.

## Langkah 1: Membuat instance ExtCodetextBuilder

Baris pertama membangun objek yang akan menampung semua fragmen. Tidak ada konfigurasi yang diperlukan pada titik ini.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Mengapa ini penting*: Menginstansiasi builder mengalokasikan buffer internal. Semua pemanggilan `add_*` berikutnya beroperasi pada buffer tersebut, menjamin urutan yang Anda tentukan.

## Langkah 2: Menambahkan data plain (tidak‑encoded)

Data plain terdiri dari karakter yang termasuk dalam set karakter default (biasanya ASCII). Gunakan `add_plain_codetext` untuk fragmen semacam itu.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Penjelasan*: String `"ABC123"` hanya berisi karakter ASCII, jadi tidak diperlukan penanda ECI. Metode ini hanya menambahkan byte mentah ke buffer internal.

## Langkah 3: Menambahkan data yang harus didahului oleh ECI

Ketika Anda perlu menyisipkan karakter Unicode—seperti Cyrillic, Jepang, atau emoji—Anda harus memberi tahu encoder set karakter mana yang harus digunakan. Ini dilakukan dengan `add_eci_codetext(eci, text)`. Argumen pertama adalah nilai ECI numerik; argumen kedua adalah teks sebenarnya.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*Mengapa ECI 3*: Menurut spesifikasi ISO/IEC 18004, ECI 3 memetakan ke UTF‑8. Dengan menyisipkan penanda ini, pembaca barcode mengetahui untuk mendekode byte berikutnya sebagai UTF‑8, mempertahankan karakter Cyrillic.

### Menangani encoding lain

Jika Anda memerlukan ISO‑8859‑1 (Eropa Barat) Anda dapat menggunakan `add_eci_codetext(4, "¡Hola!")`. Untuk Shift‑JIS (Jepang) nilai ECI adalah 20:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

Selalu pastikan bahwa library barcode target mendukung nilai ECI yang dipilih; ECI yang tidak didukung akan menyebabkan kegagalan encoding.

## Langkah 4: Mengambil string extended‑codetext yang digabungkan

Setelah semua fragmen ditambahkan, panggil `get_extended_codetext()` untuk memperoleh string akhir. String ini mencakup semua urutan escape ECI yang diperlukan.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Output yang diharapkan** (ditampilkan sebagai Python `repr` untuk kejelasan):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Rincian*:

* `ABC123` – segmen ASCII plain.  
* `\x1B\x1D\x03` – urutan escape ECI untuk UTF‑8 (ESC GS 0x03).  
* `Привет` – kata Cyrillic yang di‑encode UTF‑8.

Byte escape yang tepat dapat berbeda tergantung pada implementasi library, tetapi urutan logis selalu *plain → penanda ECI → teks Unicode*.

## Contoh lengkap yang dapat dijalankan

Menggabungkan semuanya, berikut adalah skrip mandiri yang dapat Anda salin‑tempel ke dalam file bernama `create_extended_codetext.py` dan jalankan segera.

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

Menjalankan skrip akan mencetak string yang digabungkan, siap untuk encoder barcode apa pun yang menerima input extended‑codetext.

## Kesalahan umum dan cara menghindarinya

| Gejala | Penyebab kemungkinan | Solusi |
|---|---|---|
| `UnicodeEncodeError` when calling `add_eci_codetext` | Menyediakan string yang berisi karakter yang tidak dapat direpresentasikan dalam ECI yang dipilih | Verifikasi bahwa ECI cocok dengan encoding sebenarnya dari string (mis., gunakan ECI 3 untuk teks UTF‑8 apa pun). |
| Missing ECI marker in the final output | Tidak sengaja menggunakan `add_plain_codetext` untuk data non‑ASCII | Beralih ke `add_eci_codetext` untuk karakter apa pun di luar rentang ASCII. |
| Barcode scanner shows garbled characters | Pemindai tidak mendukung nilai ECI yang dipilih | Pilih ECI yang didukung secara universal (UTF‑8 didukung luas) atau kembali ke ISO‑8859‑1 jika bahasa target memungkinkan. |
| `get_extended_codetext` returns an empty string | Tidak ada fragmen yang ditambahkan sebelum memanggil metode | Pastikan setidaknya satu pemanggilan `add_*` dieksekusi. |

### Kasus tepi: String kosong

Memanggil `add_plain_codetext("")` atau `add_eci_codetext(3, "")` tidak berbahaya; builder hanya mengabaikan fragmen kosong. Namun, pemanggilan kosong berulang dapat menghasilkan penanda ECI yang tidak diperlukan. Hindari dengan memeriksa panjang string sebelum menambahkan.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Memperluas pola untuk data dinamis

Dalam aplikasi dunia nyata Anda sering membangun extended codetext dari input pengguna atau catatan basis data. Potongan kode berikut menunjukkan loop yang memproses daftar tuple `(type, value)`, di mana `type` adalah `"plain"` atau `"eci"`.

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

Pendekatan ini skalabel dengan baik: Anda dapat membaca definisi fragmen dari JSON, CSV, atau API tanpa mengubah logika inti pembuatan.

## Menguji output

Tes unit singkat memastikan builder berperilaku seperti yang diharapkan. Menggunakan `pytest`:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

Menjalankan `pytest` harus lulus, mengonfirmasi bahwa penanda ECI muncul tepat di tempat yang seharusnya.

## Konsep terkait yang mungkin ingin Anda jelajahi selanjutnya

* **Barcode encoding libraries** – mis., `python-barcode`, `zxing` bindings, yang menerima string extended codetext secara langsung.  
* **ECI table reference** – daftar lengkap nilai ECI numerik dipublikasikan oleh ISO/IEC 18004 dan dapat disimpan sebagai dictionary Python untuk pencarian.  
* **Error correction levels** – saat menghasilkan QR code, gabungkan extended codetext dengan tingkat koreksi kesalahan yang sesuai (L, M, Q, H) untuk pemindaian yang kuat.

## Kesimpulan

Anda sekarang tahu cara **membuat extended codetext** di Python menggunakan `ExtCodetextBuilder`. Prosesnya sederhana:

1. Instansiasi builder.  
2. Tambahkan fragmen plain dan ECI‑encoded sesuai kebutuhan.  
3. Ambil string akhir dan berikan ke generator barcode Anda.

Dengan mengikuti pola di atas Anda dapat menangani campuran data ASCII dan Unicode apa pun, menghindari kesalahan encoding umum, dan menghasilkan string siap barcode yang berfungsi di berbagai pemindai. Bereksperimenlah dengan berbagai ECI, integrasikan builder ke dalam pipeline data Anda, dan Anda akan memiliki fondasi yang kuat untuk semua kebutuhan extended‑codetext Anda.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}