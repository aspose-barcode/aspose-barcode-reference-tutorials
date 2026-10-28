---
category: general
date: 2026-10-28
description: Pelajari cara mengakses kelas BuildVersionInfo dalam Aspose.Barcode Python
  SDK untuk mengambil nama produk, versi, dan tanggal rilis. Termasuk contoh kode
  lengkap dan praktik terbaik.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- access buildversioninfo class
- Aspose Barcode Python
- retrieve library version
- BuildVersionInfo example
- barcode SDK metadata
language: id
lastmod: 2026-10-28
og_description: Akses kelas BuildVersionInfo di Aspose.Barcode Python SDK untuk mendapatkan
  nama produk, versi, dan tanggal rilis. Ikuti panduan lengkap ini dengan kode yang
  dapat dijalankan.
og_image_alt: Console output showing product name, version and release date from BuildVersionInfo
  class
og_title: Cara mengakses kelas BuildVersionInfo di Aspose.Barcode untuk Python
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to access BuildVersionInfo class in Aspose.Barcode Python
    SDK to retrieve product name, version and release date. Includes full code example
    and best practices.
  headline: How to access BuildVersionInfo class in Aspose.Barcode for Python
  type: TechArticle
- description: Learn how to access BuildVersionInfo class in Aspose.Barcode Python
    SDK to retrieve product name, version and release date. Includes full code example
    and best practices.
  name: How to access BuildVersionInfo class in Aspose.Barcode for Python
  steps:
  - name: Import the class that provides build information
    text: '```python # Step 1: Import the class that provides build information from
      aspose.barcode import BuildVersionInfo ```'
  - name: Create an instance to access the library's metadata
    text: '```python # Step 2: Create an instance to access the library''s metadata
      build_info = BuildVersionInfo() ```'
  - name: Display the product name
    text: '```python # Step 3: Display the product name print("Product:", build_info.PRODUCT)
      ```'
  - name: Show the major and minor version numbers
    text: '```python # Step 4: Show the major and minor version numbers print("Version:",
      f"{build_info.PRODUCT_MAJOR}.{build_info.PRODUCT_MINOR}") ```'
  - name: Output the release date of this build
    text: '```python # Step 5: Output the release date of this build print("Release
      date:", build_info.RELEASE_DATE) ```'
  - name: Full script
    text: 'Putting all steps together yields a concise, self‑contained script:'
  - name: Verifying the SDK version at runtime
    text: 'In CI/CD pipelines you may want to abort the build if the installed version
      does not match a required minimum. The following snippet demonstrates a simple
      guard:'
  - name: Dealing with missing attributes
    text: 'Although `BuildVersionInfo` is stable, older releases (pre‑20.0) used slightly
      different attribute names. To maintain compatibility, you can fall back gracefully:'
  - name: Logging instead of printing
    text: 'For production services, replace `print` with a structured logger:'
  type: HowTo
tags:
- Aspose
- Python
- Barcode
- SDK
title: Cara mengakses kelas BuildVersionInfo di Aspose.Barcode untuk Python
url: /id/python/general/how-to-access-buildversioninfo-class-in-aspose-barcode-for-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara mengakses kelas BuildVersionInfo di Aspose.Barcode untuk Python

Jika Anda perlu **mengakses kelas BuildVersionInfo** di Aspose.Barcode Python SDK, panduan ini menunjukkan solusi lengkap yang siap dijalankan. Mengetahui nama produk yang tepat, nomor versi, dan tanggal rilis membantu Anda memverifikasi bahwa build perpustakaan yang benar telah diterapkan, yang penting untuk pemecahan masalah dan kepatuhan.

Dalam tutorial ini Anda akan belajar cara mengimpor kelas, membuat instance, dan menampilkan metadata yang disediakannya. Kami juga membahas instalasi, jebakan umum, dan cara menyesuaikan kode untuk pemeriksaan build otomatis. Pada akhir tutorial Anda akan dapat mengambil versi perpustakaan secara programatis dan mengintegrasikan informasi tersebut ke dalam log atau panel UI.

## Prasyarat

Sebelum Anda memulai, pastikan Anda memiliki:

* Python 3.8 atau yang lebih baru terpasang di mesin pengembangan Anda.  
* Akses internet untuk mengunduh paket Aspose.Barcode dari PyPI.  
* Familiaritas dasar dengan menjalankan skrip Python dari baris perintah.

Tidak ada ketergantungan sistem tambahan yang diperlukan karena Aspose.Barcode adalah distribusi murni‑Python.

## Instal Aspose.Barcode untuk Python

Langkah pertama adalah menambahkan paket Aspose.Barcode ke lingkungan Anda. Gunakan `pip` untuk menginstal rilis stabil terbaru:

```bash
pip install aspose-barcode
```

> **Pro tip:** Jika Anda bekerja di lingkungan virtual (disarankan), aktifkan terlebih dahulu sebelum menjalankan perintah untuk menghindari pencemaran paket‑site global.

Wheel `aspose-barcode` menyertakan binary native, jadi Anda tidak perlu mengompilasi apa pun secara manual.

## Cara mengakses kelas BuildVersionInfo

Setelah SDK tersedia, Anda dapat langsung menggunakan kelas `BuildVersionInfo`. Bagian‑bagian berikut menjelaskan setiap baris kode, mengapa diperlukan, dan menampilkan output yang diharapkan.

### Langkah 1: Impor kelas yang menyediakan informasi build

```python
# Step 1: Import the class that provides build information
from aspose.barcode import BuildVersionInfo
```

Kelas `BuildVersionInfo` berada di namespace `aspose.barcode`. Mengimpornya memisahkan fungsionalitas metadata dari sisa API barcode, sehingga skrip Anda tetap ringan.

### Langkah 2: Buat instance untuk mengakses metadata perpustakaan

```python
# Step 2: Create an instance to access the library's metadata
build_info = BuildVersionInfo()
```

Membuat instance kelas tidak memerlukan argumen apa pun karena metadata sudah disematkan dalam assembly pada saat build. Objek tersebut kini mengekspos beberapa atribut read‑only.

### Langkah 3: Tampilkan nama produk

```python
# Step 3: Display the product name
print("Product:", build_info.PRODUCT)
```

`PRODUCT` mengembalikan string yang dapat dibaca manusia seperti `"Aspose.Barcode for Python via .NET"` yang mengidentifikasi keluarga produk yang tepat.

### Langkah 4: Tampilkan nomor versi mayor dan minor

```python
# Step 4: Show the major and minor version numbers
print("Version:", f"{build_info.PRODUCT_MAJOR}.{build_info.PRODUCT_MINOR}")
```

`PRODUCT_MAJOR` dan `PRODUCT_MINOR` adalah bidang integer yang bersama‑sama mewakili versi semantik SDK (misalnya, `23.9`). Menggunakan f‑string menjamin format `major.minor` yang bersih.

### Langkah 5: Keluarkan tanggal rilis build ini

```python
# Step 5: Output the release date of this build
print("Release date:", build_info.RELEASE_DATE)
```

`RELEASE_DATE` menyediakan tanggal ketika binary dipaketkan, dengan format `YYYY-MM-DD`. Ini berguna untuk menghasilkan laporan kepatuhan.

### Skrip lengkap

Menggabungkan semua langkah menghasilkan skrip singkat yang berdiri sendiri:

```python
# access_buildversioninfo_example.py

# Install the SDK first:
#   pip install aspose-barcode

from aspose.barcode import BuildVersionInfo

def main() -> None:
    """Retrieve and print Aspose.Barcode library metadata."""
    build_info = BuildVersionInfo()

    print("Product:", build_info.PRODUCT)
    print("Version:", f"{build_info.PRODUCT_MAJOR}.{build_info.PRODUCT_MINOR}")
    print("Release date:", build_info.RELEASE_DATE)

if __name__ == "__main__":
    main()
```

#### Output yang diharapkan

Menjalankan skrip dengan SDK saat ini (per Oktober 2026) menghasilkan sesuatu yang mirip dengan:

```
Product: Aspose.Barcode for Python via .NET
Version: 23.9
Release date: 2026-09-15
```

Jika Anda melihat angka yang berbeda, kemungkinan Anda menggunakan build yang lebih lama atau lebih baru—gunakan output ini untuk memverifikasi bahwa versi yang diharapkan berada di produksi.

## Menangani kasus tepi dan praktik terbaik

### Memverifikasi versi SDK saat runtime

Di pipeline CI/CD Anda mungkin ingin menghentikan build jika versi yang terpasang tidak memenuhi minimum yang diperlukan. Potongan kode berikut menunjukkan guard sederhana:

```python
MIN_MAJOR = 23
MIN_MINOR = 8

if (build_info.PRODUCT_MAJOR, build_info.PRODUCT_MINOR) < (MIN_MAJOR, MIN_MINOR):
    raise RuntimeError(
        f"Unsupported Aspose.Barcode version {build_info.PRODUCT_MAJOR}.{build_info.PRODUCT_MINOR}. "
        f"Minimum required is {MIN_MAJOR}.{MIN_MINOR}."
    )
```

### Menangani atribut yang hilang

Meskipun `BuildVersionInfo` stabil, rilis lama (pra‑20.0) menggunakan nama atribut yang sedikit berbeda. Untuk mempertahankan kompatibilitas, Anda dapat melakukan fallback secara elegan:

```python
product = getattr(build_info, "PRODUCT", "Unknown")
major = getattr(build_info, "PRODUCT_MAJOR", 0)
minor = getattr(build_info, "PRODUCT_MINOR", 0)
release = getattr(build_info, "RELEASE_DATE", "N/A")
```

### Logging alih-alih mencetak

Untuk layanan produksi, ganti `print` dengan logger terstruktur:

```python
import logging

logging.basicConfig(level=logging.INFO)
logger = logging.getLogger(__name__)

logger.info("Product: %s", build_info.PRODUCT)
logger.info("Version: %s.%s", build_info.PRODUCT_MAJOR, build_info.PRODUCT_MINOR)
logger.info("Release date: %s", build_info.RELEASE_DATE)
```

Pendekatan ini terintegrasi mulus dengan kerangka kerja seperti `loguru` atau stack observabilitas cloud‑native.

## Konsep terkait yang mungkin ingin Anda jelajahi selanjutnya

* **Membuat barcode dengan Aspose.Barcode** – pelajari cara membuat QR code, Code128, dan gambar DataMatrix.  
* **Membaca metadata barcode** – gunakan `BarCodeReader` untuk mengekstrak data yang terkode dari gambar.  
* **Menyematkan info versi di UI** – tampilkan versi SDK di dasbor web menggunakan Flask atau FastAPI.  

Setiap topik ini dibangun di atas kemampuan **mengambil informasi versi perpustakaan**, memastikan Anda selalu mengetahui apa yang sedang dijalankan.

## Kesimpulan

Anda kini tahu cara **mengakses kelas BuildVersionInfo** di Aspose.Barcode Python SDK, mengambil nama produk, versi mayor/minor, dan tanggal rilis, serta menangani kasus tepi umum. Mengintegrasikan metadata ini ke dalam log atau komponen UI memberi Anda keyakinan bahwa build SDK yang tepat sedang digunakan, yang penting untuk debugging, kepatuhan, dan pengujian otomatis.

Silakan sesuaikan contoh ini untuk pipeline CI Anda, tambahkan pemeriksaan versi yang lebih canggih, atau gabungkan output dengan fitur Aspose.Barcode lainnya. Selamat coding!

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}