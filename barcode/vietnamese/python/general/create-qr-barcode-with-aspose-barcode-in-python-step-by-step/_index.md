---
category: general
date: 2026-08-09
description: Tạo mã QR trong Python bằng Aspose.BarCode. Tìm hiểu cách xây dựng codetext
  mở rộng, điều chỉnh giao diện và lưu hình ảnh—tất cả trong một hướng dẫn.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create QR barcode
- Aspose.BarCode Python
- extended codetext QR
- QR code generation Python
- barcode visual customization
language: vi
lastmod: 2026-08-09
og_description: Tạo mã QR trong Python với Aspose.BarCode. Hướng dẫn này chỉ cách
  xây dựng codetext mở rộng, thiết lập các tham số hiển thị và xuất hình ảnh.
og_image_alt: Screenshot of a generated QR barcode created with Aspose.BarCode in
  Python
og_title: Tạo mã QR bằng Aspose.BarCode trong Python – ví dụ mã đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  headline: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  type: TechArticle
- description: Create QR barcode in Python using Aspose.BarCode. Learn how to build
    extended codetext, adjust appearance, and save the image—all in one tutorial.
  name: Create QR barcode with Aspose.BarCode in Python – step‑by‑step guide
  steps:
  - name: Common variations
    text: '- **Multiple ECI segments:** Call `add_eci_codetext` multiple times to
      mix several languages. - **Different ECI identifiers:** Use `27` for ISO‑8859‑1,
      `28` for ISO‑8859‑2, etc., depending on your target encoding.'
  - name: Edge case handling
    text: '- **High‑density data:** If the encoded data is large, you may need to
      increase `x_dimension` or choose a higher error‑correction level (via `qr_generator.parameters.qr.error_correction_level`).
      - **Transparent background:** Set `qr_generator.parameters.barcode.bg_color
      = Color.Transparent` for PNGs'
  - name: Verifying the result
    text: 'Open the saved file in any image viewer. You should see a QR code that,
      when scanned, returns the combined string:'
  type: HowTo
tags:
- QR code
- Python
- Aspose
- Barcode generation
title: Tạo mã QR bằng Aspose.BarCode trong Python – hướng dẫn từng bước
url: /vi/python/general/create-qr-barcode-with-aspose-barcode-in-python-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo QR barcode với Aspose.BarCode trong Python – hướng dẫn từng bước

Nếu bạn cần **tạo QR barcode** trong Python, hướng dẫn này sẽ dẫn bạn qua toàn bộ quá trình sử dụng thư viện Aspose.BarCode. Cho dù bạn đang mã hoá ID sản phẩm, văn bản đa ngôn ngữ, hoặc dữ liệu tùy chỉnh, bạn sẽ thấy cách xây dựng một extended codetext, điều chỉnh các thiết lập hình ảnh, và lưu ảnh cuối cùng trong một script có thể chạy được.

Ví dụ cũng minh họa cách hiển thị phiên bản của thư viện, giúp bạn xác nhận rằng bạn đang chạy một bản phát hành tương thích. Khi kết thúc hướng dẫn này, bạn sẽ có một hình ảnh QR barcode sẵn sàng sử dụng và hiểu rõ từng tùy chọn cấu hình.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- Python 3.8+ đã được cài đặt.
- Gói `aspose-barcode` (cài đặt bằng `pip install aspose-barcode`).
- Kiến thức cơ bản về cú pháp Python.
- Quyền ghi vào thư mục đầu ra nơi file PNG sẽ được lưu.

> **Mẹo chuyên nghiệp:** Sử dụng môi trường ảo để tránh xung đột phiên bản với các dự án khác.

## Bước 1: Xác minh phiên bản thư viện Aspose.BarCode

Hiển thị phiên bản thư viện đảm bảo bạn đang sử dụng bản phát hành hỗ trợ extended codetext và mã hoá QR.

```python
from asposebarcode import BuildVersionInfo

# Show the current Aspose.BarCode version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)
```

**Tại sao điều này quan trọng:**  
Các bản phát hành cũ có thể thiếu lớp `ExtCodetextBuilder` cần thiết cho các đoạn plain và ECI hỗn hợp. Xác nhận phiên bản giúp ngăn ngừa lỗi thời gian chạy sau này trong quy trình.

## Bước 2: Xây dựng chuỗi extended codetext

Extended codetext cho phép bạn kết hợp dữ liệu ASCII thuần với các đoạn Unicode (ECI), điều này rất cần thiết cho các QR code đa ngôn ngữ.

```python
from asposebarcode import ExtCodetextBuilder

# Initialize the builder
ext_builder = ExtCodetextBuilder()

# Add a plain segment – typically a product ID or numeric code
ext_builder.add_plain_codetext("ABC12345")

# Add an ECI segment – here we embed Japanese greeting "こんにちは"
# 26 is the ECI identifier for UTF‑8 encoding
ext_builder.add_eci_codetext(26, "こんにちは")

# Retrieve the full extended codetext that the QR generator will use
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")
```

**Tại sao điều này quan trọng:**  
Phương thức `add_plain_codetext` lưu dữ liệu dưới dạng ASCII tiêu chuẩn, trong khi `add_eci_codetext` thêm tiền tố cho khối Unicode bằng bộ định danh ECI phù hợp. Cách tiếp cận này giúp máy quét QR giải mã đúng văn bản tiếng Nhật, tránh các ký tự bị rối.

### Các biến thể phổ biến

- **Nhiều đoạn ECI:** Gọi `add_eci_codetext` nhiều lần để trộn nhiều ngôn ngữ.
- **Các bộ định danh ECI khác nhau:** Sử dụng `27` cho ISO‑8859‑1, `28` cho ISO‑8859‑2, v.v., tùy thuộc vào mã hoá mục tiêu của bạn.

## Bước 3: Tạo QR barcode bằng extended codetext

Bây giờ chúng ta đã có một chuỗi được định dạng đúng, chúng ta có thể tạo QR code.

```python
from asposebarcode import BarCodeGenerator, EncodeTypes, BarCodeImageFormat

# Create the QR generator with the extended codetext
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)
```

**Tại sao điều này quan trọng:**  
`EncodeTypes.QR` báo cho Aspose.BarCode sử dụng ký hiệu QR. Truyền `extended_codetext` trực tiếp liên kết dữ liệu hỗn hợp với ma trận QR, bảo tồn cả phần plain và Unicode.

## Bước 4: Điều chỉnh giao diện hình ảnh (tùy chọn nhưng được khuyến nghị)

Tinh chỉnh các tham số hình ảnh của barcode cải thiện độ tin cậy khi quét và phù hợp với hướng dẫn thương hiệu.

```python
# Set module (pixel) size – larger values increase overall image size
qr_generator.parameters.barcode.x_dimension = 4      # each module = 4 pixels

# Set border thickness – a thin white border helps scanners isolate the QR code
qr_generator.parameters.barcode.border_width = 2    # 2-pixel border
```

**Tại sao điều này quan trọng:**  
- **`x_dimension`** kiểm soát kích thước của mỗi mô-đun QR; quá nhỏ có thể gây lỗi đọc trên thiết bị độ phân giải thấp.  
- **`border_width`** thêm vùng yên tĩnh. Một số máy quét yêu cầu ít nhất 4 mô-đun vùng yên tĩnh; thư viện tự động thêm, nhưng bạn có thể tăng để an toàn hơn.

### Xử lý các trường hợp biên

- **Dữ liệu mật độ cao:** Nếu dữ liệu được mã hoá lớn, bạn có thể cần tăng `x_dimension` hoặc chọn mức sửa lỗi cao hơn (qua `qr_generator.parameters.qr.error_correction_level`).  
- **Nền trong suốt:** Đặt `qr_generator.parameters.barcode.bg_color = Color.Transparent` cho PNG có kênh alpha.

## Bước 5: Lưu ảnh QR barcode

Cuối cùng, ghi ảnh ra đĩa ở định dạng bạn muốn.

```python
# Define output path – replace YOUR_DIRECTORY with an actual folder
output_file = "YOUR_DIRECTORY/extended_qr.png"

# Save as PNG; other formats include JPEG, BMP, GIF, TIFF
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

**Tại sao điều này quan trọng:**  
Lưu dưới dạng PNG giữ chất lượng không mất dữ liệu, lý tưởng cho QR code cần các cạnh sắc nét. Nếu bạn cần định dạng khác cho ứng dụng web, chỉ cần thay đổi giá trị trong enum `BarCodeImageFormat`.

### Xác minh kết quả

Mở file đã lưu bằng bất kỳ trình xem ảnh nào. Bạn sẽ thấy một QR code mà khi quét sẽ trả về chuỗi kết hợp:

```
ABC12345
こんにちは
```

Hầu hết các ứng dụng quét QR hiện đại sẽ hiển thị đoạn plain trước và sau đó hiển thị lời chào tiếng Nhật một cách chính xác.

---

## Script có thể chạy đầy đủ

Sao chép toàn bộ khối bên dưới vào một file có tên `create_qr_barcode.py` và chạy bằng `python create_qr_barcode.py`. Điều chỉnh `YOUR_DIRECTORY` thành thư mục có quyền ghi trên máy của bạn.

```python
# create_qr_barcode.py
from asposebarcode import (
    BuildVersionInfo,
    ExtCodetextBuilder,
    BarCodeGenerator,
    EncodeTypes,
    BarCodeImageFormat,
)

# 1️⃣ Display library version
version_info = BuildVersionInfo()
print(
    f"Aspose.BarCode version: {version_info.PRODUCT} "
    f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR} "
    f"(released {version_info.RELEASE_DATE})"
)

# 2️⃣ Build extended codetext (plain + Japanese Unicode)
ext_builder = ExtCodetextBuilder()
ext_builder.add_plain_codetext("ABC12345")
ext_builder.add_eci_codetext(26, "こんにちは")
extended_codetext = ext_builder.get_extended_codetext()
print(f"Generated extended codetext: {extended_codetext}")

# 3️⃣ Create QR generator
qr_generator = BarCodeGenerator(EncodeTypes.QR, extended_codetext)

# 4️⃣ Optional visual tweaks
qr_generator.parameters.barcode.x_dimension = 4
qr_generator.parameters.barcode.border_width = 2

# 5️⃣ Save image
output_file = "YOUR_DIRECTORY/extended_qr.png"
qr_generator.save(output_file, BarCodeImageFormat.PNG)
print(f"Barcode saved to {output_file}")
```

Chạy script này sẽ in ra phiên bản, extended codetext, và xác nhận rằng file PNG đã được tạo.

---

## Kết luận

Bạn giờ đã biết cách **tạo QR barcode** trong Python bằng Aspose.BarCode. Hướng dẫn đã bao gồm:

1. Xác minh phiên bản thư viện.  
2. Xây dựng extended codetext với các đoạn plain và ECI (Unicode).  
3. Tạo QR code.  
4. Tùy chỉnh các tham số hình ảnh như kích thước mô-đun và độ rộng viền.  
5. Lưu ảnh cuối cùng ở định dạng PNG.

Từ đây bạn có thể khám phá:

- Thay đổi mức sửa lỗi (`qr_generator.parameters.qr.error_correction_level`).  
- Thêm logo hoặc ảnh nền (`qr_generator.parameters.qr.logo`).  
- Xuất ra các định dạng khác như SVG cho đồ họa web có thể mở rộng.  
- Tích hợp trình tạo vào endpoint Flask hoặc Django để tạo QR ngay lập tức.

Thử nghiệm với các payload dữ liệu và thiết lập hình ảnh khác nhau để phù hợp với thương hiệu và yêu cầu quét của ứng dụng của bạn. Chúc bạn lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [How to Create Barcode Quiet Zone for ITF-14 Using Aspose.BarCode for .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}