---
category: general
date: 2026-09-13
description: Pelajari cara menggunakan BuildVersionInfo di Aspose.BarCode untuk Python
  untuk mengekstrak versi produk dan metadata lainnya dalam beberapa langkah sederhana.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use buildversioninfo
- extract product version
language: id
lastmod: 2026-09-13
og_description: Gunakan BuildVersionInfo di Aspose.BarCode untuk Python untuk mengekstrak
  versi produk, versi assembly, dan tanggal rilis dengan panduan langkah demi langkah
  yang jelas.
og_image_alt: Screenshot showing use BuildVersionInfo output with version details
og_title: Gunakan BuildVersionInfo di Python – ekstrak versi produk dengan cepat
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to use BuildVersionInfo in Aspose.BarCode for Python to extract
    product version and other metadata in a few simple steps.
  headline: How to use BuildVersionInfo to extract product version in Python
  type: TechArticle
tags:
- Aspose
- Python
- Barcode
- VersionInfo
title: Cara menggunakan BuildVersionInfo untuk mengekstrak versi produk di Python
url: /id/python/general/how-to-use-buildversioninfo-to-extract-product-version-in-py/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cara menggunakan BuildVersionInfo untuk mengekstrak versi produk di Python

Jika Anda perlu **menggunakan BuildVersionInfo** untuk membaca metadata Aspose.BarCode, panduan ini menunjukkan secara tepat cara melakukannya. Pada akhir tutorial Anda akan dapat **mengekstrak informasi versi produk**, versi assembly, versi file, dan tanggal rilis hanya dengan beberapa baris kode.

Banyak pengembang memperlakukan data versi sebagai hal yang dipikirkan belakangan, padahal memiliki versi yang tepat pada runtime membantu dalam debugging, logging, dan pemeriksaan kepatuhan. Tutorial ini membahas cara menginstal paket, membuat objek `BuildVersionInfo`, mengambil setiap properti, dan mencetak laporan yang bersih. Tidak diperlukan dokumentasi eksternal—semua yang Anda butuhkan ada di sini.

## Prasyarat

Sebelum Anda mulai, pastikan Anda memiliki:

* Python 3.8 atau yang lebih baru terinstal.
* Akses ke paket **Aspose.BarCode for Python via .NET** (modul `aspose.barcode`).
* Pemahaman dasar tentang import Python dan pernyataan `print`.

Jika Anda belum menginstal pustaka tersebut, jalankan:

```bash
pip install aspose-barcode
```

Langkah‑langkah di bawah mengasumsikan paket tersedia di lingkungan Anda.

## Langkah 1: Impor paket Aspose.BarCode

Hal pertama yang harus Anda lakukan adalah mengimpor namespace `aspose.barcode`. Ini memberi Anda akses ke semua kelas, termasuk `BuildVersionInfo`.

```python
# Step 1: Import the Aspose.BarCode package
import aspose.barcode as bc
```

> **Mengapa ini penting:** Mengimpor paket mendaftarkan assembly .NET dengan Python, memungkinkan kelas `BuildVersionInfo` diinstansiasi. Melewatkan import akan menghasilkan `ModuleNotFoundError`.

## Langkah 2: Gunakan BuildVersionInfo untuk mengambil metadata pustaka

Sekarang Anda dapat **menggunakan BuildVersionInfo** untuk menanyakan detail versi yang disematkan Aspose pada saat build. Membuat objek tidak memerlukan argumen apa pun.

```python
# Step 2: Create a BuildVersionInfo object to query library metadata
version_info = bc.BuildVersionInfo()
```

> **Penjelasan:** Konstruktor `BuildVersionInfo` memuat field statis dari assembly yang mendasarinya. Ini adalah objek ringan, hanya‑baca, sehingga Anda dapat menggunakannya kembali di seluruh aplikasi Anda dengan aman.

## Langkah 3: Ekstrak detail versi produk

Dengan instance `version_info` di tangan, Anda dapat **mengekstrak versi produk** dan properti terkait. Setiap atribut mengembalikan string yang dapat Anda simpan, log, atau bandingkan.

```python
# Step 3: Retrieve individual version properties from the object
assembly_version = version_info.ASSEMBLY_VERSION   # e.g., "23.12.0.0"
file_version     = version_info.FILE_VERSION       # e.g., "23.12.0.0"
product_title    = version_info.PRODUCT            # e.g., "Aspose.BarCode for Python via .NET"
major_version    = version_info.PRODUCT_MAJOR      # e.g., "23"
minor_version    = version_info.PRODUCT_MINOR      # e.g., "12"
release_date     = version_info.RELEASE_DATE       # e.g., "2023-12-01"
```

> **Mengapa Anda memerlukan setiap field**
> * **Assembly version** – mengidentifikasi versi biner yang tepat dimuat pada runtime.
> * **File version** – cocok dengan resource versi file; berguna untuk pemeriksaan properti file Windows.
> * **Product title** – nama yang dapat dibaca manusia dan dapat ditampilkan di log UI.
> * **Major / Minor version** – memungkinkan Anda menerapkan logika kondisional berdasarkan rentang versi.
> * **Release date** – membantu Anda memverifikasi bahwa Anda menjalankan build terbaru, yang penting untuk patch keamanan.

### Kasus tepi: atribut yang hilang

Jika versi Aspose di masa depan menghapus suatu atribut, mengaksesnya akan menimbulkan `AttributeError`. Lindungi kode Anda dengan menggunakan `getattr` beserta nilai default:

```python
assembly_version = getattr(version_info, "ASSEMBLY_VERSION", "unknown")
```

## Langkah 4: Tampilkan informasi versi yang terkumpul

Akhirnya, cetak data yang dikumpulkan dalam format yang rapi dan teralign. Langkah ini opsional tetapi memperlihatkan cara Anda dapat mencatat info versi saat aplikasi mulai.

```python
# Step 4: Display the gathered version information
print("Assembly version :", assembly_version)
print("File version     :", file_version)
print("Product title    :", product_title)
print("Major version    :", major_version)
print("Minor version    :", minor_version)
print("Release date     :", release_date)
```

**Output yang diharapkan** (nilai akan berbeda tergantung pada versi pustaka yang terinstal):

```
Assembly version : 23.12.0.0
File version     : 23.12.0.0
Product title    : Aspose.BarCode for Python via .NET
Major version    : 23
Minor version    : 12
Release date     : 2023-12-01
```

> **Pro tip:** Arahkan output ini ke file log atau sematkan dalam dialog “About” aplikasi Anda untuk memberi pengguna akhir akses cepat ke detail versi.

## Contoh lengkap yang dapat dijalankan

Menggabungkan semua bagian, berikut skrip mandiri yang dapat Anda salin‑tempel dan jalankan langsung:

```python
import aspose.barcode as bc

def show_aspose_version():
    """
    Retrieves and prints Aspose.BarCode version information using BuildVersionInfo.
    """
    version_info = bc.BuildVersionInfo()

    # Safely fetch each attribute, falling back to 'unknown' if the field vanishes
    assembly_version = getattr(version_info, "ASSEMBLY_VERSION", "unknown")
    file_version     = getattr(version_info, "FILE_VERSION", "unknown")
    product_title    = getattr(version_info, "PRODUCT", "unknown")
    major_version    = getattr(version_info, "PRODUCT_MAJOR", "unknown")
    minor_version    = getattr(version_info, "PRODUCT_MINOR", "unknown")
    release_date     = getattr(version_info, "RELEASE_DATE", "unknown")

    print("Assembly version :", assembly_version)
    print("File version     :", file_version)
    print("Product title    :", product_title)
    print("Major version    :", major_version)
    print("Minor version    :", minor_version)
    print("Release date     :", release_date)

if __name__ == "__main__":
    show_aspose_version()
```

Menjalankan skrip ini pada mesin dengan `aspose-barcode` terinstal akan mencetak blok versi yang ditunjukkan sebelumnya.

## Pertanyaan umum dan variasi

| Question | Answer |
|----------|--------|
| **What if I need the version in a JSON payload?** | Serialize the dictionary: <br>`import json; print(json.dumps({...}, indent=2))` |
| **Can I compare versions programmatically?** | Convert `major_version` and `minor_version` to integers and compare `<` or `>` as needed. |
| **Does this work on Linux/macOS?** | Yes. The .NET core runtime used by Aspose.BarCode is cross‑platform, so the same Python code runs everywhere. |
| **How to handle a missing Aspose installation?** | Wrap the import in a try/except block and provide a helpful error message: <br>`except ImportError: print("Aspose.BarCode is not installed. Run pip install aspose-barcode")` |

## Tips untuk penggunaan produksi

* **Cache objek `BuildVersionInfo`** jika Anda memerlukan data versi berulang kali; objek ini murah untuk disimpan dalam variabel level modul.
* **Log pada level INFO** selama run normal dan beralih ke DEBUG untuk output yang lebih detail.
* **Kombinasikan dengan diagnostik Aspose lainnya** (misalnya, `License.IsValid`) untuk membuat endpoint health‑check yang komprehensif.

## Kesimpulan

Anda kini tahu cara **menggunakan BuildVersionInfo** di Python untuk **mengekstrak versi produk** dan metadata terkait dari pustaka Aspose.BarCode. Skrip lengkap menunjukkan pendekatan bersih dan defensif yang bekerja lintas platform serta menangani kemungkinan perubahan API di masa depan.

Selanjutnya, Anda dapat menjelajahi:

* Menggunakan versi yang diambil untuk menegakkan persyaratan versi minimum sebelum mengaktifkan fitur barcode premium.
* Mengintegrasikan pemeriksaan versi ke dalam pipeline CI/CD untuk secara otomatis memverifikasi bahwa build Aspose.BarCode terbaru telah dideploy.
* Memperluas skrip untuk mengambil informasi lisensi (`bc.License`) guna laporan diagnostik runtime yang lengkap.

Selamat coding, dan pastikan aplikasi Anda selalu sadar versi!

## Apa yang Harus Anda Pelajari Selanjutnya?


Tutorial berikut mencakup topik yang berhubungan erat dan membangun di atas teknik yang ditunjukkan dalam panduan ini. Setiap sumber daya menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah‑demi‑langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda sendiri.

- [How to Print Version of Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [How to Set License in Aspose.BarCode for Python – Complete Guide](/barcode/english/python/general/how-to-set-license-in-aspose-barcode-for-python-complete-gui/)
- [Create barcode png in Python – Full Aspose.Barcode Guide](/barcode/english/python-java/general/create-barcode-png-in-python-full-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}