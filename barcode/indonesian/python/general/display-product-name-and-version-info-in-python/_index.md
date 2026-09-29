---
category: general
date: 2026-09-29
description: Tampilkan nama produk dalam Python sambil mencetak tanggal rilis dan
  mengambil detail versi dari pustaka barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- display product name
- print release date
- how to get version
- how to print product
- show minor version
language: id
lastmod: 2026-09-29
og_description: Tampilkan nama produk di Python dan pelajari cara mencetak tanggal
  rilis, mendapatkan versi, serta menampilkan versi minor dengan beberapa baris kode.
og_image_alt: Screenshot of terminal output showing product name, version, and release
  date
og_title: Tampilkan nama produk dan info versi di Python
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Display product name in Python while printing release date and retrieving
    version details from the barcode library.
  headline: Display product name and version info in Python
  type: TechArticle
tags:
- Python
- barcode library
- version information
title: Tampilkan nama produk dan info versi di Python
url: /id/python/general/display-product-name-and-version-info-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tampilkan nama produk dan info versi di Python

Jika Anda perlu **menampilkan nama produk** dari sebuah pustaka, panduan ini menunjukkan secara tepat cara melakukannya. Anda juga akan belajar untuk **menampilkan tanggal rilis**, **cara mendapatkan versi**, dan **menampilkan versi minor** menggunakan kode Python yang ringkas.

Banyak pengembang mengintegrasikan fitur pemindaian atau pembuatan barcode dan harus menampilkan metadata pustaka kepada pengguna atau log. Tutorial ini mencakup semua yang diperlukan untuk mengambil dan menyajikan informasi tersebut secara andal.

## Apa yang akan Anda pelajari

* Mengambil informasi versi dari pustaka `barcode`.  
* **Menampilkan nama produk** bersama dengan nomor versi mayor dan minor.  
* **Menampilkan tanggal rilis** dalam format yang mudah dibaca manusia.  
* Menangani atribut yang hilang dengan elegan.  

**Prasyarat**  
* Python 3.8 atau lebih baru.  
* Akses ke paket `barcode` (pasang dengan `pip install python-barcode` atau pustaka yang menyediakan `BuildVersionInfo`).  

---

## Cara menampilkan nama produk dan info versi di Python

Langkah pertama adalah mengimpor pustaka dan memanggil metode yang mengembalikan objek versi‑info. Objek tersebut berisi atribut seperti `PRODUCT`, `PRODUCT_MAJOR`, `PRODUCT_MINOR`, dan `RELEASE_DATE`.

```python
import barcode

def main():
    # Step 1: Retrieve version information from the barcode library
    info = barcode.BuildVersionInfo()

    # Step 2: Display product name
    print(f"Product: {info.PRODUCT}")

    # Step 3: Show major and minor version numbers
    print(f"Version: {info.PRODUCT_MAJOR}.{info.PRODUCT_MINOR}")

    # Step 4: Print release date
    print(f"Release date: {info.RELEASE_DATE}")

if __name__ == "__main__":
    main()
```

**Mengapa ini berhasil**  
`BuildVersionInfo()` mengembalikan objek ringan yang atributnya diisi pada saat impor. Mengakses atribut secara langsung menghindari I/O tambahan dan menjamin bahwa data yang ditampilkan cocok dengan versi pustaka yang sebenarnya digunakan kode Anda.

### Output yang diharapkan

```
Product: BarcodeLib
Version: 2.5
Release date: 2024-03-15
```

Nilai sebenarnya bergantung pada versi pustaka barcode yang terpasang.

---

## Cara mendapatkan versi dari pustaka barcode

Jika Anda hanya membutuhkan nomor versi, Anda dapat melewatkan penampilan nama produk dan fokus pada bidang numerik.

```python
import barcode

info = barcode.BuildVersionInfo()
major = info.PRODUCT_MAJOR
minor = info.PRODUCT_MINOR

print(f"Current version: {major}.{minor}")
```

*​Atribut `PRODUCT_MAJOR` dan `PRODUCT_MINOR` mengikuti semantic versioning, memungkinkan Anda membandingkan versi secara programatis.*

---

## Cara menampilkan tanggal rilis

Tanggal rilis disimpan sebagai string dalam format `YYYY‑MM‑DD`. Untuk menampilkannya dalam locale yang berbeda, ubah terlebih dahulu menjadi objek `datetime`.

```python
import barcode
from datetime import datetime

info = barcode.BuildVersionInfo()
raw_date = info.RELEASE_DATE          # e.g., "2024-03-15"
date_obj = datetime.strptime(raw_date, "%Y-%m-%d")
formatted = date_obj.strftime("%B %d, %Y")  # "March 15, 2024"

print(f"Release date: {formatted}")
```

**Tip:** Selalu validasi string tanggal sebelum diparsing untuk menghindari `ValueError` ketika pustaka mengubah formatnya.

---

## Tampilkan versi minor bersamaan dengan versi mayor

Kadang-kadang Anda perlu menampilkan versi minor secara terpisah, misalnya saat mencatat peringatan kompatibilitas.

```python
import barcode

info = barcode.BuildVersionInfo()
print(f"Major version: {info.PRODUCT_MAJOR}")
print(f"Minor version: {info.PRODUCT_MINOR}")
```

**Pro tip:** Gunakan versi minor untuk memicu feature flags:

```python
if info.PRODUCT_MINOR >= 5:
    enable_new_feature()
```

---

## Menangani atribut yang hilang (kasus tepi)

Rilis lama dari pustaka barcode mungkin tidak mengekspos semua atribut. Bungkus akses atribut dengan `getattr` menggunakan nilai default yang masuk akal.

```python
import barcode

info = barcode.BuildVersionInfo()

product = getattr(info, "PRODUCT", "Unknown Product")
major = getattr(info, "PRODUCT_MAJOR", 0)
minor = getattr(info, "PRODUCT_MINOR", 0)
release = getattr(info, "RELEASE_DATE", "N/A")

print(f"Product: {product}")
print(f"Version: {major}.{minor}")
print(f"Release date: {release}")
```

Pola ini memastikan skrip Anda tidak pernah crash karena bidang yang hilang, menjadikannya kuat untuk pipeline CI yang mungkin dijalankan terhadap berbagai versi pustaka.

---

## Contoh lengkap yang dapat dijalankan

Berikut adalah skrip lengkap yang menggabungkan semua praktik terbaik: validasi atribut, pemformatan tanggal, dan output yang jelas.

```python
import barcode
from datetime import datetime

def fetch_info():
    """Retrieve version info safely, providing defaults for missing attributes."""
    raw = barcode.BuildVersionInfo()
    return {
        "product": getattr(raw, "PRODUCT", "Unknown Product"),
        "major": getattr(raw, "PRODUCT_MAJOR", 0),
        "minor": getattr(raw, "PRODUCT_MINOR", 0),
        "release_raw": getattr(raw, "RELEASE_DATE", "N/A")
    }

def format_release(date_str):
    """Convert YYYY‑MM‑DD to a friendly format; fall back to the original string."""
    try:
        dt = datetime.strptime(date_str, "%Y-%m-%d")
        return dt.strftime("%B %d, %Y")
    except (ValueError, TypeError):
        return date_str

def main():
    info = fetch_info()

    # Display product name
    print(f"Product: {info['product']}")

    # Show major and minor version numbers
    print(f"Version: {info['major']}.{info['minor']}")

    # Print release date in a readable form
    print(f"Release date: {format_release(info['release_raw'])}")

if __name__ == "__main__":
    main()
```

Menjalankan skrip ini pada sistem dengan pustaka barcode terpasang menghasilkan output serupa dengan contoh sebelumnya, namun kini melindungi dari bidang yang hilang dan memformat tanggal dengan baik.

---

## Kesimpulan

Anda sekarang tahu cara **menampilkan nama produk**, **menampilkan tanggal rilis**, **cara mendapatkan versi**, **cara menampilkan produk**, dan **menampilkan versi minor** menggunakan alur kerja Python yang sederhana. Contoh lengkap menunjukkan akses atribut yang dapat diandalkan, penanganan tanggal, dan perbandingan versi—keterampilan yang dapat Anda gunakan kembali untuk pustaka pihak ketiga mana pun yang mengekspos objek metadata.

**Langkah selanjutnya**

* Jelajahi metode metadata lain dari pustaka barcode, seperti `BuildCommitInfo()`.  
* Integrasikan output ke dalam kerangka logging (mis., `logging.info`).  
* Bandingkan versi secara programatis untuk menegakkan versi minimum yang diperlukan dalam aplikasi Anda.

Silakan bereksperimen dengan format output yang berbeda atau memperluas skrip untuk menulis informasi ke file untuk keperluan audit. Selamat coding!  

![Output terminal yang menampilkan nama produk dan detail versi](image.png "Output terminal")

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik yang terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber mencakup contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan menjelajahi pendekatan implementasi alternatif dalam proyek Anda.

- [menampilkan nama produk menggunakan pustaka Python barcode – panduan langkah‑demi‑langkah](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)
- [Cara Menampilkan Versi Aspose.Barcode (Python)](/barcode/english/python/general/how-to-print-version-of-aspose-barcode-python/)
- [Cara menghasilkan barcode dengan Aspose.BarCode di Python](/barcode/english/python-java/general/how-to-generate-barcode-with-aspose-barcode-in-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}