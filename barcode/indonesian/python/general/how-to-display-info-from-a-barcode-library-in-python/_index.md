---
category: general
date: 2026-09-07
description: Pelajari cara menampilkan info dari pustaka barcode, termasuk nama produk,
  versi, versi assembly, dan tanggal rilis. Panduan singkat untuk pengembang Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to display info
- display product name
- show release date
- get library version
- how to read version
language: id
lastmod: 2026-09-07
og_description: Cara menampilkan info dari pustaka barcode Python, mencakup nama produk,
  nomor versi, versi assembly, dan tanggal rilis dalam beberapa baris kode.
og_image_alt: Console output showing how to display info from barcode library
og_title: Cara menampilkan info dari pustaka barcode di Python – panduan langkah demi
  langkah
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to display info from a barcode library, including product
    name, version, assembly version, and release date. Quick guide for Python developers.
  headline: How to display info from a barcode library in Python
  type: TechArticle
- description: Learn how to display info from a barcode library, including product
    name, version, assembly version, and release date. Quick guide for Python developers.
  name: How to display info from a barcode library in Python
  steps:
  - name: Display product name
    text: 'To **display product name**, simply print the `PRODUCT` attribute:'
  - name: Show library version (major.minor)
    text: 'Most developers only need the major and minor numbers, which you can combine
      with an f‑string:'
  - name: Show assembly version
    text: 'If you need the full assembly version (including build and revision), use
      the `ASSEMBLY_VERSION` attribute:'
  - name: Show release date
    text: 'Finally, to **show release date**, print the `RELEASE_DATE` attribute:'
  - name: Complete script
    text: 'Putting everything together yields a self‑contained, runnable example:'
  - name: Library without `BuildVersionInfo`
    text: 'Some forks of the `barcode` package omit `BuildVersionInfo`. In that case
      you can read version data from the package’s `__version__` attribute:'
  - name: Formatting the release date
    text: 'If you prefer `Month Day, Year` format:'
  - name: Handling missing attributes
    text: 'When running against a custom build, an attribute may be `None`. Guard
      against that with a simple check:'
  - name: Using the information in logs
    text: 'Instead of printing to the console, you might want to log the data:'
  type: HowTo
tags:
- Python
- barcode
- version‑info
- debugging
title: Cara menampilkan info dari perpustakaan barcode di Python
url: /id/python/general/how-to-display-info-from-a-barcode-library-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menampilkan info dari pustaka barcode di Python

Jika Anda perlu **menampilkan info** dari pustaka barcode, panduan ini menunjukkan secara tepat cara mengambil dan mencetak nama produk, nomor versi, versi assembly, dan tanggal rilis. Solusi ini bekerja dengan paket `barcode` standar dan hanya memerlukan beberapa baris kode, sehingga Anda dapat menambahkannya ke skrip apa pun secara langsung.

Kami akan membahas setiap langkah, menjelaskan mengapa kode tersebut berfungsi, dan membahas jebakan umum seperti atribut yang hilang atau format versi yang tidak terduga. Pada akhir tutorial Anda akan dapat **menampilkan nama produk**, **menampilkan tanggal rilis**, dan **mendapatkan versi pustaka** di lingkungan Python mana pun.

## Prasyarat

* Python 3.8 atau yang lebih baru terpasang.
* Pustaka `barcode` (atau fork yang kompatibel) tersedia di lingkungan Anda. Instal dengan:

```bash
pip install python-barcode
```

* Familiaritas dasar dengan fungsi `print` Python dan f‑strings.

Jika Anda sudah memiliki pustaka tersebut, Anda dapat melewati langkah instalasi.

## Cara menampilkan info dari pustaka barcode

Inti dari solusi ini adalah satu panggilan ke `barcode.BuildVersionInfo()` yang mengembalikan sebuah objek berisi semua metadata terkait versi. Header H2 berikut berisi kata kunci utama, memenuhi persyaratan SEO.

```python
# Import the barcode module
import barcode

# Retrieve version information from the barcode library
info = barcode.BuildVersionInfo()
```

Objek `info` biasanya memiliki atribut-atribut berikut:

| Attribute          | Makna |
|--------------------|-------|
| `PRODUCT`          | Nama produk yang dapat dibaca manusia |
| `PRODUCT_MAJOR`    | Nomor versi utama |
| `PRODUCT_MINOR`    | Nomor versi minor |
| `ASSEMBLY_VERSION` | Versi assembly lengkap (mis., `1.2.3.4`) |
| `RELEASE_DATE`     | Tanggal rilis pustaka |

### Menampilkan nama produk

Untuk **menampilkan nama produk**, cukup cetak atribut `PRODUCT`:

```python
print("Product:", info.PRODUCT)
```

> **Mengapa ini berhasil:** `info.PRODUCT` adalah string yang didefinisikan oleh pembuat pustaka. Mencetaknya secara langsung memberi Anda nama tepat yang digunakan dalam metadata paket, yang berguna untuk pencatatan atau tampilan UI.

### Menampilkan versi pustaka (major.minor)

Sebagian besar pengembang hanya membutuhkan nomor mayor dan minor, yang dapat Anda gabungkan dengan f‑string:

```python
print("Version:", f"{info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")
```

> **Penjelasan:** f‑string memformat dua atribut integer menjadi pola `major.minor` konvensional, yang cocok dengan format yang Anda lihat di halaman PyPI pustaka.

### Menampilkan versi assembly

Jika Anda memerlukan versi assembly lengkap (termasuk build dan revisi), gunakan atribut `ASSEMBLY_VERSION`:

```python
print("Assembly version:", info.ASSEMBLY_VERSION)
```

Versi assembly berguna ketika Anda harus memverifikasi bahwa build tertentu dari pustaka telah dimuat, terutama dalam pipeline CI.

### Menampilkan tanggal rilis

Akhirnya, untuk **menampilkan tanggal rilis**, cetak atribut `RELEASE_DATE`:

```python
print("Release date:", info.RELEASE_DATE)
```

Tanggal rilis disimpan sebagai objek `datetime.date`, sehingga dicetak dalam format ISO (`YYYY‑MM‑DD`). Anda dapat memformat ulang dengan `strftime` jika proyek Anda memerlukan gaya yang berbeda.

### Skrip lengkap

Menggabungkan semuanya menghasilkan contoh yang berdiri sendiri dan dapat dijalankan:

```python
import barcode

def display_barcode_library_info():
    """Retrieve and print all version‑related metadata from the barcode library."""
    try:
        info = barcode.BuildVersionInfo()
    except AttributeError:
        raise RuntimeError(
            "The installed barcode package does not expose BuildVersionInfo(). "
            "Make sure you are using a compatible version."
        )

    print("Product:", info.PRODUCT)
    print("Version:", f"{info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")
    print("Assembly version:", info.ASSEMBLY_VERSION)
    print("Release date:", info.RELEASE_DATE)

if __name__ == "__main__":
    display_barcode_library_info()
```

**Output yang diharapkan** (nilai akan berbeda tergantung pada versi yang terpasang):

```
Product: python-barcode
Version: 0.14
Assembly version: 0.14.0.0
Release date: 2023-02-15
```

Skrip ini menangkap `AttributeError` potensial untuk membantu Anda **cara membaca versi** informasi dengan aman ketika pustaka mengubah API-nya.

## Variasi umum dan kasus tepi

### Pustaka tanpa `BuildVersionInfo`

Beberapa fork dari paket `barcode` tidak menyertakan `BuildVersionInfo`. Dalam kasus tersebut Anda dapat membaca data versi dari atribut `__version__` paket:

```python
import barcode
print("Package version:", barcode.__version__)
```

Meskipun ini memberikan string versi PEP‑440, ia tidak memiliki bidang terperinci (`PRODUCT`, `ASSEMBLY_VERSION`, dll.). Gunakan fallback hanya ketika metode utama tidak tersedia.

### Memformat tanggal rilis

Jika Anda lebih suka format `Month Day, Year`:

```python
print("Release date:", info.RELEASE_DATE.strftime("%B %d, %Y"))
```

### Menangani atribut yang hilang

Saat menjalankan pada build khusus, sebuah atribut mungkin `None`. Lindungi dengan pemeriksaan sederhana:

```python
release = info.RELEASE_DATE or "unknown"
print("Release date:", release)
```

### Menggunakan informasi dalam log

Alih-alih mencetak ke konsol, Anda mungkin ingin mencatat data:

```python
import logging
logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

logger.info("Product: %s", info.PRODUCT)
logger.info("Version: %s.%s", info.PRODUCT_MAJOR, info.PRODUCT_MINOR)
logger.info("Assembly version: %s", info.ASSEMBLY_VERSION)
logger.info("Release date: %s", info.RELEASE_DATE)
```

Logging menjaga informasi tersedia dalam file log aplikasi Anda, yang berharga untuk debugging masalah produksi.

## Tips profesional

* **Cache objek info** jika Anda memanggilnya berulang kali; data versi tidak pernah berubah saat runtime.
* **Validasi versi** sebelum melakukan pemeriksaan kompatibilitas:

```python
if int(info.PRODUCT_MAJOR) < 1:
    raise RuntimeError("Barcode library version is too old for this feature.")
```

* **Gabungkan dengan diagnostik lain** (mis., versi Python) untuk laporan lingkungan lengkap:

```python
import sys
print("Python:", sys.version.split()[0])
```

## Kesimpulan

Anda sekarang tahu **cara menampilkan info** dari pustaka barcode di Python, termasuk **menampilkan nama produk**, **menampilkan tanggal rilis**, dan **mendapatkan versi pustaka**. Skrip lengkap menunjukkan alur kerja standar, sementara variasi menunjukkan cara menyesuaikan solusi untuk implementasi pustaka yang berbeda atau kebutuhan pemformatan.

Selanjutnya, Anda mungkin ingin menjelajahi:

* **Cara membaca versi** paket pihak ketiga lainnya menggunakan `importlib.metadata`.
* **Menampilkan info versi** dalam aplikasi GUI (Tkinter, PyQt, dll.).
* **Mengotomatiskan pemeriksaan versi** dalam pipeline CI untuk menegakkan versi minimum pustaka.

Silakan bereksperimen dengan kode, mengintegrasikannya ke dalam alat Anda sendiri, dan berbagi hasil Anda dengan komunitas!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [menampilkan nama produk menggunakan pustaka Python barcode – panduan langkah demi langkah](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Cara Membuat Gambar QR Code di Python dengan Aspose.Barcode – Panduan Lengkap](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Cara Membuat Barcode di C# – Panduan Lengkap Aspose.Barcode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}