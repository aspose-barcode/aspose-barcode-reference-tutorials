---
category: general
date: 2026-10-24
description: Contoh generator barcode yang menunjukkan cara membuat barcode Planet
  dan cara mengatur tinggi barcode menggunakan Python. Ikuti panduan langkah demi
  langkah.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to create planet barcode
- how to set barcode height
language: id
lastmod: 2026-10-24
og_description: Contoh generator barcode yang menunjukkan cara membuat barcode Planet
  dan cara mengatur tinggi barcode di Python. Dapatkan solusi lengkap yang dapat dijalankan.
og_image_alt: Barcode generator example showing Planet and RM4SCC barcodes with different
  heights
og_title: Contoh generator kode batang – buat kode batang Planet dan RM4SCC
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  headline: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  type: TechArticle
- description: Barcode generator example that shows how to create Planet barcode and
    how to set barcode height using Python. Follow the step‑by‑step guide.
  name: Barcode generator example – create Planet and RM4SCC barcodes with custom
    height
  steps:
  - name: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
    text: '**Instantiate** a `BarcodeGenerator` with the desired `EncodeTypes` value
      and the data string.'
  - name: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
    text: '**Configure** the X‑dimension (module width) and, when needed, the barcode
      height.'
  - name: '**Save** the image to disk in PNG format.'
    text: '**Save** the image to disk in PNG format.'
  type: HowTo
tags:
- barcode
- Python
- image generation
title: Contoh generator kode batang – buat kode batang Planet dan RM4SCC dengan tinggi
  khusus
url: /id/python-java/general/barcode-generator-example-create-planet-and-rm4scc-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Contoh generator barcode – buat barcode Planet dan RM4SCC dengan tinggi khusus

Jika Anda mencari **contoh generator barcode**, panduan ini memberikan solusi lengkap yang siap dijalankan. Anda akan melihat **cara membuat gambar barcode planet**, mempelajari **cara mengatur tinggi barcode**, dan memahami perbedaan kecil antara penyesuaian otomatis dan manual. Tutorial ini membahas dua skenario realistis: barcode Planet yang menggunakan tinggi default (otomatis), dan barcode RM4SCC di mana tinggi dipaksa menjadi 100 px. Pada akhir tutorial Anda dapat menghasilkan file PNG untuk jenis barcode yang didukung dengan satu API yang konsisten.

## Prasyarat

* Python 3.8 atau lebih baru terinstal.
* Paket `aspose-barcode` (atau perpustakaan apa pun yang menyediakan `BarcodeGenerator`, `EncodeTypes`, dan `BarCodeImageFormat`). Instal dengan  

  ```bash
  pip install aspose-barcode
  ```
* Izin menulis ke folder tempat file PNG akan disimpan.

Tidak ada ketergantungan sistem tambahan yang diperlukan.

## Gambaran solusi

Inti dari **contoh generator barcode** terdiri dari tiga langkah yang dapat digunakan kembali:

1. **Instantiate** sebuah `BarcodeGenerator` dengan nilai `EncodeTypes` yang diinginkan dan string data.
2. **Configure** X‑dimension (lebar modul) dan, bila diperlukan, tinggi barcode.
3. **Save** gambar ke disk dalam format PNG.

Kedua contoh berbagi langkah 1 dan 3; hanya langkah 2 yang berbeda karena barcode Planet mengandalkan perhitungan tinggi otomatis dari perpustakaan, sementara barcode RM4SCC menunjukkan **cara mengatur tinggi barcode** secara manual.

Berikut adalah diagram tingkat tinggi yang menggambarkan alur:

![Contoh generator barcode yang menampilkan barcode Planet dan RM4SCC dengan tinggi yang berbeda.](barcode-example.png)

## Cara membuat barcode planet – tinggi otomatis

Barcode Planet merupakan bagian dari keluarga pos yang digunakan oleh banyak layanan pos nasional. Dalam kebanyakan kasus Anda membiarkan SDK menentukan tinggi, sehingga proporsi visual tetap benar untuk panjang data yang bervariasi.

```python
# Step 1: Create a generator for the Planet barcode with the data "123456"
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

planet_gen = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Define the X‑dimension (module width) as 4 pixels
planet_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Save the barcode image as a PNG file
planet_gen.save("PostalPlanetBarHeightAuto.png", BarCodeImageFormat.Png)
```

**Mengapa ini berhasil**

* `EncodeTypes.Planet` memberi tahu perpustakaan untuk menggunakan simbol Planet.
* Menetapkan `x_dimension.pixels` menjadi 4 memberikan setiap modul lebar 4 px, yang merupakan default umum untuk label cetak.
* Tidak ada tinggi yang ditetapkan secara eksplisit; SDK menghitung tinggi optimal berdasarkan data dan X‑dimension, itulah mengapa ini merupakan **contoh generator barcode** paling sederhana untuk kode pos.

**Hasil yang diharapkan**

File PNG 2‑D bernama `PostalPlanetBarHeightAuto.png` yang berisi barcode Planet yang tajam. Tinggi akan sekitar 30 px (tergantung versi perpustakaan) dan lebar akan menjadi 4 px × jumlah modul.

## Cara mengatur tinggi barcode – contoh RM4SCC khusus

RM4SCC adalah barcode pos lain yang sering memerlukan tinggi tetap untuk menyesuaikan template label. Bagian tutorial ini menunjukkan **cara mengatur tinggi barcode** ke jumlah piksel yang tepat.

```python
# Step 1: Create a generator for the RM4SCC barcode with the data "123456"
rm4scc_gen = BarcodeGenerator(EncodeTypes.RM4SCC, "123456")

# Step 2: Set the X‑dimension to 4 pixels (same as the Planet example)
rm4scc_gen.parameters.barcode.x_dimension.pixels = 4

# Step 3: Specify the barcode height as 100 pixels
rm4scc_gen.parameters.barcode.bar_height.pixels = 100

# Step 4: Save the barcode image as a PNG file
rm4scc_gen.save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png)
```

**Mengapa ini berhasil**

* `EncodeTypes.RM4SCC` memilih simbol RM4SCC.
* X‑dimension tetap pada 4 px untuk menjaga ukuran modul konsisten di kedua barcode.
* `bar_height.pixels = 100` memaksa barcode memiliki tinggi tepat 100 px, menggantikan perhitungan otomatis. Ini adalah cara yang direkomendasikan **mengatur tinggi barcode** ketika tata letak Anda memerlukan ukuran tertentu.

**Hasil yang diharapkan**

File PNG bernama `PostalRM4SCCBarHeight100Pixels.png` yang menampilkan barcode RM4SCC tinggi. Lebar masih ditentukan oleh X‑dimension, sementara tinggi tetap 100 px, menjadikannya cocok untuk printer label resolusi tinggi.

## Skrip lengkap – gabungkan kedua contoh

Jika Anda lebih suka satu skrip yang menghasilkan kedua gambar, salin kode berikut ke dalam `generate_barcodes.py` dan jalankan.

```python
"""
Full barcode generator example that creates:
* a Planet barcode with automatic height
* an RM4SCC barcode with a custom 100 px height
"""

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

def create_planet_barcode(data: str, x_dim: int, out_path: str):
    """Generate a Planet barcode using the default height."""
    gen = BarcodeGenerator(EncodeTypes.Planet, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.save(out_path, BarCodeImageFormat.Png)

def create_rm4scc_barcode(data: str, x_dim: int, height_px: int, out_path: str):
    """Generate an RM4SCC barcode with a fixed height."""
    gen = BarcodeGenerator(EncodeTypes.RM4SCC, data)
    gen.parameters.barcode.x_dimension.pixels = x_dim
    gen.parameters.barcode.bar_height.pixels = height_px
    gen.save(out_path, BarCodeImageFormat.Png)

if __name__ == "__main__":
    # Planet barcode – auto height
    create_planet_barcode(
        data="123456",
        x_dim=4,
        out_path="PostalPlanetBarHeightAuto.png"
    )

    # RM4SCC barcode – custom 100 px height
    create_rm4scc_barcode(
        data="123456",
        x_dim=4,
        height_px=100,
        out_path="PostalRM4SCCBarHeight100Pixels.png"
    )
```

**Penjelasan skrip**

* Dua fungsi pembantu menjaga kode tetap DRY (Don’t Repeat Yourself) dan memudahkan memperluas skrip untuk simbol lainnya.
* Guard `if __name__ == "__main__":` memungkinkan file diimpor sebagai modul tanpa mengeksekusi logika pembuatan, yang berguna untuk pengujian unit.
* Semua parameter (string data, X‑dimension, tinggi) bersifat eksplisit, sehingga skrip berfungsi sebagai referensi **contoh generator barcode** untuk proyek di masa mendatang.

## Pertanyaan umum dan kasus tepi

| Question | Answer |
|----------|--------|
| *Bagaimana jika saya membutuhkan X‑dimension yang berbeda?* | Ubah `x_dimension.pixels` ke lebar modul yang diinginkan. Nilai yang lebih besar meningkatkan ukuran keseluruhan barcode secara proporsional. |
| *Apakah saya dapat menghasilkan format gambar lain?* | Ya. Ganti `BarCodeImageFormat.Png` dengan `Jpg`, `Bmp`, atau `Gif` tergantung pada enum perpustakaan. |
| *Apa yang terjadi jika string data berisi karakter tidak valid?* | Generator akan melempar `ArgumentException`. Validasi data terhadap set karakter simbol sebelum memanggil konstruktor. |
| *Apakah memungkinkan mengatur tinggi minimum sambil tetap menggunakan auto‑scaling?* | Gunakan `gen.parameters.barcode.bar_height.min_pixels = <value>` (jika SDK menyediakan properti `min_pixels`). Ini mencegah barcode menyusut di bawah ukuran yang dapat dibaca. |
| *Apakah saya perlu membuang (dispose) generator?* | Kelas `BarcodeGenerator` mengimplementasikan `IDisposable` di .NET; di Python garbage collector menangani, tetapi Anda dapat memanggil `gen.dispose()` jika membuat banyak instance dalam loop. |

## Tips untuk penggunaan produksi

* **Pro tip:** Simpan nilai X‑dimension dan tinggi dalam file konfigurasi sehingga Anda dapat menyesuaikannya tanpa harus mengkompilasi ulang.
* **Waspadai:** Menggunakan tinggi yang terlalu kecil untuk simbol yang dipilih; pemindai mungkin gagal membaca barcode.
* **Catatan kinerja:** Menghasilkan batch besar barcode lebih cepat ketika Anda menggunakan kembali satu instance `BarcodeGenerator` dan hanya mengubah properti `code_text` di antara penyimpanan.

## Kesimpulan

**Contoh generator barcode** ini menunjukkan baik **cara membuat gambar barcode planet** dengan penyesuaian otomatis maupun **cara mengatur tinggi barcode** secara manual untuk kode RM4SCC. Dengan mengikuti panduan langkah demi langkah, Anda dapat mengintegrasikan pembuatan barcode ke dalam aplikasi Python apa pun, menyesuaikan dimensi, dan menghasilkan file PNG siap untuk pencetakan atau tampilan digital.

### Langkah selanjutnya

* Jelajahi simbol tambahan seperti `EncodeTypes.Postnet` atau `EncodeTypes.Code128` – pola yang sama berlaku.
* Bereksperimen dengan **cara mengatur tinggi barcode** untuk kode QR atau simbol DataMatrix; sebagian besar perpustakaan menyediakan properti `bar_height` yang serupa.
* Gabungkan generator dengan perpustakaan PDF untuk menyematkan barcode langsung ke dalam faktur atau label pengiriman.

Silakan sesuaikan skrip, bagikan hasil Anda, dan beri tahu kami jenis barcode apa yang akan Anda tambahkan selanjutnya!

## Apa yang Harus Anda Pelajari Selanjutnya?

Tutorial berikut mencakup topik terkait erat yang membangun teknik yang ditunjukkan dalam panduan ini. Setiap sumber menyertakan contoh kode lengkap yang berfungsi dengan penjelasan langkah demi langkah untuk membantu Anda menguasai fitur API tambahan dan mengeksplorasi pendekatan implementasi alternatif dalam proyek Anda.

- [Cara menyimpan PNG dari contoh generator barcode di Python](/barcode/english/python-java/general/how-to-save-png-from-a-barcode-generator-example-in-python/)
- [Cara membuat PNG barcode planet dengan Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [Cara menggunakan generator barcode C# untuk membuat barcode Planet](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}