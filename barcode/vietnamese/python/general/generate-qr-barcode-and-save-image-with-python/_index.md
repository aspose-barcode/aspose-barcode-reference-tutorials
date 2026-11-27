---
category: general
date: 2026-11-27
description: Tạo mã QR trong Python bằng Aspose.Barcode và học cách lưu nhanh hình
  ảnh mã vạch vào ổ đĩa.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate QR barcode
- save barcode image
- Aspose.Barcode Python
- extended codetext QR
- barcode version information
language: vi
lastmod: 2026-11-27
og_description: Tạo mã QR trong Python với Aspose.Barcode và lưu ngay hình ảnh mã
  vạch. Tham khảo ví dụ đầy đủ để tạo, tùy chỉnh và lưu trữ mã QR.
og_image_alt: Screenshot of a generated QR barcode created with Python
og_title: Tạo mã QR và lưu hình ảnh bằng Python – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate QR barcode in Python using Aspose.Barcode and learn how to
    save barcode image to disk quickly.
  headline: Generate QR barcode and save image with Python
  type: TechArticle
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Tạo mã QR và lưu ảnh bằng Python
url: /vi/python/general/generate-qr-barcode-and-save-image-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch QR và lưu hình ảnh bằng Python

Nếu bạn cần **generate QR barcode** trong một ứng dụng Python, hướng dẫn này sẽ chỉ cho bạn cách thực hiện bằng thư viện Aspose.Barcode. Bạn cũng sẽ học cách **save barcode image** đúng vào thư mục cục bộ, lấy thông tin phiên bản thư viện, và xử lý các đoạn codetext mở rộng.

Việc tạo mã QR là một yêu cầu phổ biến cho các hệ thống bán vé, thanh toán di động và theo dõi sản phẩm. Khi kết thúc tutorial này, bạn sẽ có một script sẵn sàng chạy, tạo ra một file hình ảnh mã vạch QR và in thông tin phiên bản để gỡ lỗi hoặc đáp ứng yêu cầu tuân thủ.

## Yêu cầu trước

* Cài đặt Python 3.8 hoặc mới hơn.
* Gói `aspose-barcode`. Cài đặt bằng `pip install aspose-barcode`.
* Quyền ghi vào thư mục sẽ lưu hình ảnh mã vạch.

Không cần dịch vụ bên ngoài nào thêm; toàn bộ quá trình chạy cục bộ.

## Bước 1: Xây dựng codetext mở rộng với `ExtCodetextBuilder`

Codetext mở rộng cho phép bạn kết hợp văn bản thuần và các đoạn ECI (Extended Channel Interpretation) trong một mã QR duy nhất. Điều này hữu ích khi bạn cần nhúng các ký tự từ các bộ mã khác nhau, chẳng hạn như ký hiệu Euro.

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# Create the builder instance
ext_builder = ExtCodetextBuilder()

# Add a plain text segment
ext_builder.add_plain_codetext("ABC123")

# Add an ECI segment that uses ISO‑IEC 8859‑1 (code page 3)
ext_builder.add_eci_codetext(3, "€123")
```

**Tại sao bước này quan trọng:**  
`ExtCodetextBuilder` lắp ráp chuỗi cuối cùng mà bộ mã hoá QR sẽ xử lý. Nếu không xây dựng codetext mở rộng, mã vạch sẽ chỉ chứa các ký tự ASCII thuần và không thể biểu diễn các ký hiệu đặc thù của địa phương.

## Bước 2: Lấy chuỗi codetext mở rộng đã kết hợp

```python
# Get the final extended codetext that will be encoded
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Kết quả đầu ra trông như sau:

```
Extended codetext: ABC123[ECI3]€123
```

Dấu hiệu `[ECI3]` trong ngoặc vuông thông báo cho bộ mã hoá QR chuyển sang bộ ký tự đã chỉ định cho các ký tự tiếp theo.

## Bước 3: Tạo mã vạch QR bằng cách sử dụng codetext mở rộng

```python
# Create a QR barcode generator with the extended codetext
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)
```

**Giải thích:**  
`BarcodeGenerator` nhận hai đối số: loại mã vạch (`QR`) và dữ liệu cần mã hoá (`extended_codetext`). Trình tạo chuẩn bị tất cả các cấu trúc nội bộ cần thiết để render.

## Bước 4: Lưu hình ảnh mã vạch đã tạo

```python
# Define the output path – adjust the folder as needed
output_path = "output/qr_extended.png"

# Save the image in PNG format
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")
```

**Tại sao bạn nên dùng cách này:**  
Gọi `save` trực tiếp sẽ ghi hình ảnh vào đĩa bằng định dạng được suy ra từ phần mở rộng tệp. Phương thức này hỗ trợ PNG, JPEG, BMP và TIFF, mang lại sự linh hoạt cho các bên tiêu thụ downstream khác nhau.

### Xác minh hình ảnh đã lưu

Mở tệp `output/qr_extended.png` bằng bất kỳ trình xem ảnh nào. Bạn sẽ thấy một mã QR mà khi quét sẽ trả về chuỗi `ABC123€123`. Hầu hết các trình quét QR trên điện thoại hiện đại sẽ tự động xử lý đoạn ECI.

## Bước 5: Truy vấn thông tin phiên bản Aspose.BarCode (tùy chọn nhưng hữu ích)

Biết chính xác phiên bản của thư viện Aspose.BarCode giúp khi bạn cần báo cáo lỗi hoặc xác minh tính tương thích.

```python
# Retrieve version details
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Kết quả điển hình:

```
Aspose.BarCode version:
  Assembly version : 23.9.0.0
  File version     : 23.9.0
  Product          : Aspose.BarCode for Python via .NET
  Release date     : 2023-09-15
```

## Toàn bộ script – sao chép, dán và chạy

```python
import aspose.barcode as bc
from aspose.barcode.generation import ExtCodetextBuilder, BuildVersionInfo

# 1️⃣ Build extended codetext
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC123")
ext_builder.add_eci_codetext(3, "€123")
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 2️⃣ Generate QR barcode
barcode = bc.BarcodeGenerator(bc.EncodeTypes.QR, extended_codetext)

# 3️⃣ Save barcode image
output_path = "output/qr_extended.png"
barcode.save(output_path)
print(f"Barcode image saved to {output_path}")

# 4️⃣ Display version information
version_info = BuildVersionInfo()
print("Aspose.BarCode version:")
print(f"  Assembly version : {version_info.ASSEMBLY_VERSION}")
print(f"  File version     : {version_info.FILE_VERSION}")
print(f"  Product          : {version_info.PRODUCT}")
print(f"  Release date     : {version_info.RELEASE_DATE}")
```

Chạy script sẽ tạo ra hình ảnh mã QR và in cả codetext mở rộng và chi tiết phiên bản ra console.

## Các biến thể phổ biến và trường hợp đặc biệt

| Tình huống | Điều chỉnh đề xuất |
|-----------|------------------------|
| **Different character set** | Thay đổi định danh ECI được truyền vào `add_eci_codetext`. Đối với UTF‑8 dùng `5`. |
| **Higher error correction** | Đặt `barcode.parameters.barcode.qr_error_level = bc.QRErrorLevel.H` trước khi gọi `save`. |
| **Custom image size** | Sử dụng `barcode.parameters.image_width` và `barcode.parameters.image_height` để kiểm soát kích thước pixel. |
| **Non‑PNG output** | Thay đổi phần mở rộng tệp trong `output_path` thành `.jpg` hoặc `.bmp`. Thư viện sẽ tự động chọn bộ mã hoá phù hợp. |

## Mẹo chuyên nghiệp

* **Tạo thư mục đầu ra** một cách lập trình nếu nó có thể chưa tồn tại:

  ```python
  import os
  os.makedirs(os.path.dirname(output_path), exist_ok=True)
  ```

* **Xác thực mã QR** sau khi tạo bằng cách đọc lại bằng `aspose.barcode.BarcodeReader`. Điều này đảm bảo dữ liệu đã mã hoá khớp với mong đợi, đặc biệt khi sử dụng các đoạn ECI.

  ```python
  reader = bc.BarcodeReader(output_path, bc.DecodeType.QR)
  for result in reader.read():
      print("Decoded text:", result.code_text)
  ```

* **Mẹo hiệu năng** – tái sử dụng một đối tượng `BarcodeGenerator` duy nhất nếu bạn cần tạo nhiều mã QR trong vòng lặp. Đặt lại thuộc tính `code_text` thay vì tạo đối tượng mới mỗi lần lặp.

## Kết luận

Bây giờ bạn đã biết cách **generate QR barcode** trong Python với Aspose.Barcode, xây dựng một codetext mở rộng kết hợp văn bản thuần và các đoạn ECI, và đúng cách **save barcode image** vào đĩa. Script cũng cho thấy cách lấy thông tin phiên bản thư viện để khắc phục sự cố.

Những bước tiếp theo bạn có thể khám phá bao gồm:

* Thêm logo hoặc màu tùy chỉnh lên mã QR.
* Nhúng mã vạch QR trực tiếp vào PDF bằng Aspose.PDF.
* Tự động hoá việc tạo hàng loạt cho các bộ dữ liệu lớn.

Hãy thoải mái thử nghiệm với các payload dữ liệu khác nhau, mức độ sửa lỗi và định dạng ảnh. Chúc lập trình vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [How to generate Code 128 barcode and save barcode image with Aspose.BarCode](/barcode/english/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/)
- [How to generate DataMatrix barcode in Python with Aspose.BarCode](/barcode/english/python/general/how-to-generate-datamatrix-barcode-in-python-with-aspose-bar/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}