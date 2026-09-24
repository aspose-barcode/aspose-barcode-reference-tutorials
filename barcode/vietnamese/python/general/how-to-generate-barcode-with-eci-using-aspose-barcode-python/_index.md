---
category: general
date: 2026-08-19
description: Cách tạo mã vạch với ECI bằng Aspose.Barcode cho Python. Tìm hiểu cách
  thêm dữ liệu ECI, kết hợp văn bản thường và lưu hình ảnh trong một hướng dẫn rõ
  ràng.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- how to add eci
- Aspose.Barcode Python
- extended codetext barcode
- ECI encoding Python
language: vi
lastmod: 2026-08-19
og_description: Cách tạo mã vạch với ECI bằng Aspose.Barcode cho Python. Hãy theo
  dõi hướng dẫn này để học cách thêm dữ liệu ECI, tùy chỉnh giao diện và lưu kết quả.
og_image_alt: Screenshot showing a barcode generated with how to generate barcode
  example
og_title: Cách tạo mã vạch với ECI bằng Aspose.Barcode Python – từng bước
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  headline: How to generate barcode with ECI using Aspose.Barcode Python
  type: TechArticle
- description: How to generate barcode with ECI using Aspose.Barcode for Python. Learn
    how to add eci data, mix plain text, and save the image in one clear guide.
  name: How to generate barcode with ECI using Aspose.Barcode Python
  steps:
  - name: Expected result
    text: When you open `extended_codetext.png`, you should see a Code 128 barcode
      that encodes the numeric string `1234567890` followed by the Chinese characters
      “特殊字符”. Scanning the barcode with a modern scanner that respects ECI will return
      the original mixed string.
  - name: What if I need a different character set?
    text: Choose the appropriate ECI value from the ISO/IEC 18004 table. For example,
      ECI 27 represents ISO‑8859‑1 (Latin‑1). Replace the numeric identifier in `add_eci_codetext`
      accordingly.
  - name: Can I embed more than one ECI block?
    text: Yes. Call `add_eci_codetext` multiple times. The builder inserts the necessary
      ECI switch codes between blocks, preserving the order you add them.
  - name: Does the generator support QR codes with ECI?
    text: Absolutely. Replace `barcode.Symbology.CODE_128` with `barcode.Symbology.QR`
      and adjust any QR‑specific parameters (e.g., error correction level) via `generator.parameters.qr`.
  - name: How to handle very long data strings?
    text: For linear barcodes like Code 128, the maximum length is about 80 characters
      when using extended codetext. If you exceed that, consider switching to a two‑dimensional
      symbology such as QR or Data Matrix, which can store thousands of characters.
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Cách tạo mã vạch với ECI bằng Aspose.Barcode Python
url: /vi/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch với ECI bằng Aspose.Barcode Python

Nếu bạn cần biết **cách tạo mã vạch** chứa cả ký tự thường và dữ liệu được mã hoá bằng ECI, hướng dẫn này sẽ trình bày toàn bộ quy trình. Bạn sẽ thấy chính xác **cách thêm eci** vào các phần, điều chỉnh kích thước và ghi hình ảnh ra đĩa với một script duy nhất có thể chạy.

Hướng dẫn bao gồm:

* Lấy phiên bản thư viện Aspose.Barcode (tùy chọn nhưng hữu ích cho việc gỡ lỗi).  
* Xây dựng chuỗi codetext mở rộng kết hợp ký tự thường và ký tự được mã hoá bằng ECI.  
* Tạo trình tạo mã vạch cho một symbology hỗ trợ codetext mở rộng.  
* Tùy chỉnh kích thước mã vạch và lưu file PNG cuối cùng.

Không cần tài liệu bên ngoài; sao chép mã, chạy nó, và bạn sẽ có một hình ảnh mã vạch bao gồm các ký tự Trung Quốc được mã hoá với ECI 26 (UTF‑8).

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* Python 3.8 hoặc mới hơn đã được cài đặt.  
* Gói `aspose-barcode` đã được cài đặt (`pip install aspose-barcode`).  
* Quyền ghi vào thư mục nơi bạn dự định lưu file PNG.

Nếu bạn đang sử dụng môi trường ảo, hãy kích hoạt nó trước để giữ các phụ thuộc được cô lập.

## Bước 1: Xác minh phiên bản Aspose.Barcode (tùy chọn)

Biết chính xác phiên bản thư viện giúp khi bạn cần báo cáo lỗi hoặc so sánh tính năng giữa các phiên bản.

```python
import aspose.barcode as barcode
from aspose.barcode.generation import BuildVersionInfo

ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)
```

*Lý do quan trọng*: Đầu ra phiên bản xác nhận rằng môi trường chạy khớp với tài liệu bạn đang theo dõi. Các phiên bản khác nhau có thể hỗ trợ các giá trị ECI khác nhau, vì vậy đây là một kiểm tra nhanh.

## Bước 2: Xây dựng codetext mở rộng với phần thường và phần được mã hoá bằng ECI

Aspose.Barcode cung cấp `ExtCodetextBuilder` để nối dữ liệu thường và các đoạn được mã hoá bằng ECI. Trong ví dụ này chúng ta kết hợp một chuỗi số với các ký tự Trung Quốc.

```python
from aspose.barcode.generation import ExtCodetextBuilder

builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using ECI 26 (UTF‑8)
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)
```

*Giải thích*:  
* `add_plain_codetext` chèn dữ liệu mà symbology của mã vạch coi là ký tự thông thường.  
* `add_eci_codetext` yêu cầu trình tạo thêm chỉ báo ECI (ở đây **26**, tương ứng với UTF‑8) trước văn bản được cung cấp. Đây chính là **cách thêm eci** vào dữ liệu mã vạch.

Bạn có thể gọi `add_eci_codetext` nhiều lần để nhúng nhiều khối ngôn ngữ khác nhau. Builder sẽ tự động xử lý các chuỗi escape cần thiết.

## Bước 3: Chọn một symbology hỗ trợ codetext mở rộng

Không phải mọi loại mã vạch đều có thể lưu các đoạn ECI. Code 128, QR và Data Matrix là các lựa chọn phổ biến. Ví dụ sử dụng Code 128 vì nó được hỗ trợ rộng rãi và hoạt động tốt cho dữ liệu hỗn hợp alphanumeric.

```python
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,   # Code128 supports extended codetext
    extended_codetext
)
```

*Tại sao lại là Code 128?*: Nó chấp nhận toàn bộ dải ASCII và các chuỗi escape ECI do builder tạo ra, làm cho nó trở thành lựa chọn lý tưởng cho kịch bản “cách tạo mã vạch” mà kết hợp văn bản thường và đã mã hoá.

## Bước 4: Điều chỉnh giao diện mã vạch

Bạn có thể kiểm soát kích thước, chiều cao, lề và nhiều khía cạnh hình ảnh khác qua đối tượng `parameters`.

```python
# Width of a single module (the smallest bar)
generator.parameters.barcode.x_dimension = 2   # 2 pixels per module

# Height of the bars (for linear barcodes)
generator.parameters.barcode.bar_height = 50  # 50 pixels tall

# Optional: add quiet zone (margin) if required by a scanner
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10   # 10 pixels margin on each side
```

*Mẹo*: Nếu bạn dự định in mã vạch, tăng `x_dimension` và `bar_height` một cách tỷ lệ để duy trì khả năng đọc ở DPI mục tiêu.

## Bước 5: Lưu hình ảnh mã vạch

Cuối cùng, ghi hình ảnh đã tạo ra vào một tệp. Aspose.Barcode hỗ trợ PNG, JPEG, BMP và nhiều định dạng khác.

```python
output_path = "output/extended_codetext.png"
generator.save(output_path)
print(f"Barcode saved as {output_path}")
```

Đảm bảo thư mục `output` tồn tại hoặc tạo nó bằng `os.makedirs("output", exist_ok=True)` trước khi gọi `save`.

### Kết quả mong đợi

Khi bạn mở `extended_codetext.png`, bạn sẽ thấy một mã vạch Code 128 mã hoá chuỗi số `1234567890` tiếp theo là các ký tự Trung Quốc “特殊字符”. Quét mã vạch bằng một máy quét hiện đại hỗ trợ ECI sẽ trả về chuỗi hỗn hợp gốc.

![Mã vạch được tạo với ví dụ cách tạo mã vạch](https://example.com/images/barcode-sample.png){: .align-center alt="Mã vạch được tạo với ví dụ cách tạo mã vạch"}

## Câu hỏi thường gặp và các trường hợp đặc biệt

### Nếu tôi cần một bộ ký tự khác thì sao?

Chọn giá trị ECI phù hợp từ bảng ISO/IEC 18004. Ví dụ, ECI 27 đại diện cho ISO‑8859‑1 (Latin‑1). Thay thế định danh số trong `add_eci_codetext` cho phù hợp.

### Tôi có thể nhúng hơn một khối ECI không?

Có. Gọi `add_eci_codetext` nhiều lần. Builder sẽ chèn các mã chuyển đổi ECI cần thiết giữa các khối, giữ nguyên thứ tự bạn thêm chúng.

### Trình tạo có hỗ trợ mã QR với ECI không?

Chắc chắn. Thay thế `barcode.Symbology.CODE_128` bằng `barcode.Symbology.QR` và điều chỉnh bất kỳ tham số đặc thù QR nào (ví dụ, mức sửa lỗi) qua `generator.parameters.qr`.

```python
generator.parameters.qr.error_correction_level = barcode.QRErrorLevel.H
```

### Làm sao xử lý các chuỗi dữ liệu rất dài?

Đối với các mã vạch tuyến tính như Code 128, độ dài tối đa khoảng 80 ký tự khi sử dụng codetext mở rộng. Nếu vượt quá, hãy cân nhắc chuyển sang symbology hai chiều như QR hoặc Data Matrix, có thể lưu hàng ngàn ký tự.

## Script đầy đủ, có thể chạy

Dưới đây là chương trình hoàn chỉnh bạn có thể sao chép‑dán vào tệp có tên `generate_extended_barcode.py` và chạy trực tiếp.

```python
import os
import aspose.barcode as barcode
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# ------------------------------------------------------------------
# Optional: print library version – useful for troubleshooting
# ------------------------------------------------------------------
ver = BuildVersionInfo()
print("Assembly version :", ver.ASSEMBLY_VERSION)
print("Product version  :", f"{ver.PRODUCT_MAJOR}.{ver.PRODUCT_MINOR}")
print("Release date     :", ver.RELEASE_DATE)

# ------------------------------------------------------------------
# Build extended codetext: plain numbers + Chinese characters (ECI 26)
# ------------------------------------------------------------------
builder = ExtCodetextBuilder()
builder.add_plain_codetext("1234567890")          # plain numeric data
builder.add_eci_codetext(26, "特殊字符")          # Chinese characters using UTF‑8
extended_codetext = builder.get_extended_codetext()
print("Extended codetext :", extended_codetext)

# ------------------------------------------------------------------
# Create a Code128 generator – supports the extended codetext format
# ------------------------------------------------------------------
generator = barcode.generator.BarcodeGenerator(
    barcode.Symbology.CODE_128,
    extended_codetext
)

# ------------------------------------------------------------------
# Customize appearance (size, quiet zone, etc.)
# ------------------------------------------------------------------
generator.parameters.barcode.x_dimension = 2
generator.parameters.barcode.bar_height = 50
generator.parameters.barcode.is_quiet_zone_visible = True
generator.parameters.barcode.quiet_zone = 10

# ------------------------------------------------------------------
# Ensure output directory exists and save the image
# ------------------------------------------------------------------
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)
output_path = os.path.join(output_dir, "extended


## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo hình ảnh mã vạch với tùy chỉnh không gian bổ sung bằng Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Cách tạo hình ảnh mã vạch trong Java với Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [Cách tạo mã DataMatrix với Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}