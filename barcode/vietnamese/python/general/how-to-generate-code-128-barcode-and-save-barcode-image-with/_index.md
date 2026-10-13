---
category: general
date: 2026-09-23
description: Tìm hiểu cách tạo mã vạch Code 128 và lưu hình ảnh mã vạch bằng Aspose.BarCode
  trong Python – hướng dẫn từng bước.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate code 128 barcode
- save barcode image
- Aspose.BarCode Python
- extended codetext builder
- barcode PNG export
language: vi
lastmod: 2026-09-23
og_description: Tạo mã vạch Code 128 và lưu hình ảnh mã vạch bằng Aspose.BarCode trong
  Python. Tham khảo ví dụ đầy đủ này để tạo, tùy chỉnh và xuất mã vạch dưới dạng tệp
  PNG.
og_image_alt: Python-generated Code 128 barcode saved as PNG image
og_title: Tạo mã vạch Code 128 và lưu hình ảnh mã vạch – Hướng dẫn Python
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to generate Code 128 barcode and save barcode image using
    Aspose.BarCode in Python – step‑by‑step guide.
  headline: How to generate Code 128 barcode and save barcode image with Aspose.BarCode
  type: TechArticle
tags:
- barcode
- Code 128
- Python
- Aspose
title: Cách tạo mã vạch Code 128 và lưu hình ảnh mã vạch bằng Aspose.BarCode
url: /vi/python/general/how-to-generate-code-128-barcode-and-save-barcode-image-with/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch Code 128 và lưu hình ảnh mã vạch bằng Aspose.BarCode

Nếu bạn cần **tạo mã vạch Code 128** và **lưu hình ảnh mã vạch** trong một dự án Python, hướng dẫn này sẽ chỉ ra các bước chính xác. Sử dụng `ExtCodetextBuilder` của Aspose.BarCode, bạn có thể nhúng văn bản thuần và các đoạn Unicode trong một payload duy nhất, sau đó render kết quả thành tệp PNG.

Bạn sẽ thấy một script hoàn chỉnh, có thể chạy được, giải thích từng dòng, và các mẹo cho những vấn đề thường gặp như xử lý mã hóa ECI hoặc chọn thư mục đầu ra đúng. Không cần tài liệu bên ngoài—chỉ cần sao chép, dán và chạy.

## Yêu cầu trước

* Đã cài đặt Python 3.8+.
* Gói `aspose.barcode` (cài đặt bằng `pip install aspose-barcode`).
* Quyền ghi vào thư mục sẽ lưu PNG.

Mã này hoạt động với bất kỳ biểu tượng nào được Aspose.BarCode hỗ trợ, nhưng ví dụ tập trung vào **Code 128** vì nó mã hoá dữ liệu alphanumeric một cách hiệu quả và hỗ trợ các bộ ký tự mở rộng.

## Bước 1: Nhập các lớp cần thiết

```python
import barcode                     # Core Aspose.BarCode namespace
from barcode import BarCodeWriter, BarCodeEncodeMode, BarCodeImageFormat
from barcode import ExtCodetextBuilder, BuildVersionInfo
```

*Tại sao cần bước này?* Việc nhập các lớp cho phép bạn truy cập vào builder cho codetext mở rộng, writer tạo hình ảnh, và helper phiên bản có thể hữu ích khi gỡ lỗi các cập nhật thư viện.

## Bước 2: Xây dựng codetext mở rộng

```python
# Create a builder for extended codetext
builder = ExtCodetextBuilder()

# Add plain text (no ECI) – this part is simple ASCII
builder.add_plain_codetext("ABC123")

# Add a Unicode segment with ECI 0x03 (UTF‑8). The word “Пример” means “Example” in Russian.
builder.add_eci_codetext(0x03, "Пример")

# Retrieve the full extended codetext string
extended_codetext = builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

`ExtCodetextBuilder` cho phép bạn kết hợp dữ liệu ASCII thuần và Unicode trong một payload mã vạch duy nhất. Byte ECI (Extended Channel Interpretation) `0x03` thông báo cho máy quét rằng các byte tiếp theo được mã hoá UTF‑8, điều này rất quan trọng đối với các ngôn ngữ như tiếng Nga, tiếng Trung hoặc tiếng Ả Rập.

## Bước 3: Cấu hình barcode writer cho Code 128

```python
writer = BarCodeWriter()
writer.encode_type = BarCodeEncodeMode.CODE_128   # Choose Code 128 symbology
writer.code_text = extended_codetext
```

Cài đặt `encode_type` thành `CODE_128` chỉ dẫn cho writer render một **mã vạch Code 128**. Thuộc tính `code_text` nhận chuỗi mở rộng được xây dựng ở bước trước.

## Bước 4: Lưu hình ảnh mã vạch dưới dạng PNG

```python
output_path = "YOUR_DIRECTORY/extended_codetext.png"
writer.save(output_path, BarCodeImageFormat.PNG)
print(f"Barcode image saved to {output_path}")
```

Phương thức `save` ghi mã vạch vào tệp. Sử dụng `BarCodeImageFormat.PNG` đảm bảo nén không mất dữ liệu và tương thích rộng rãi với các ứng dụng web và di động.

## Bước 5 (tùy chọn): Xác minh phiên bản thư viện Aspose.BarCode

```python
version_info = BuildVersionInfo()
print("Assembly version :", version_info.ASSEMBLY_VERSION)
print("Product version   :", f"{version_info.PRODUCT_MAJOR}.{version_info.PRODUCT_MINOR}")
print("Release date      :", version_info.RELEASE_DATE)
```

Biết chính xác phiên bản thư viện giúp khi bạn cần báo cáo lỗi hoặc so sánh hành vi giữa các phiên bản.

## Kết quả mong đợi

Chạy script sẽ tạo ra đầu ra console tương tự như:

```
Extended codetext: ABC123[ECI=03]Пример
Assembly version : 23.12.0.0
Product version   : 23.12
Release date      : 2023-12-01
Barcode image saved to YOUR_DIRECTORY/extended_codetext.png
```

PNG được tạo (`extended_codetext.png`) trông như sau:

![Mã vạch Code 128 được tạo bằng Python và lưu dưới dạng ảnh PNG](images/code128_extended.png)

*Hình ảnh hiển thị một mã vạch Code 128 mã hoá cả chuỗi ASCII `ABC123` và từ tiếng Nga “Пример”.*

## Các câu hỏi thường gặp và xử lý các trường hợp đặc biệt

| Question | Answer |
|----------|--------|
| **Tôi có thể sử dụng biểu tượng khác không?** | Có. Thay `BarCodeEncodeMode.CODE_128` bằng bất kỳ chế độ hỗ trợ nào khác như `QR`, `EAN_13`, hoặc `PDF_417`. |
| **Nếu văn bản Unicode của tôi chứa emoji thì sao?** | Emoji cũng là ký tự UTF‑8, vì vậy lời gọi `add_eci_codetext` vẫn hoạt động. Đảm bảo máy quét mục tiêu hỗ trợ ECI bạn sử dụng. |
| **Làm sao để thay đổi kích thước ảnh?** | Đặt `writer.x_dimension` và `writer.bar_height` trước khi gọi `save`. |
| **Thư mục nào nên dùng cho `output_path`?** | Bất kỳ thư mục nào mà tiến trình Python có thể ghi được. Sử dụng `os.makedirs` với `exist_ok=True` để tạo tự động. |

## Mẹo chuyên nghiệp

* **Tránh mã hoá đường dẫn cứng.** Sử dụng `os.path.join` và `Path` từ mô-đun `pathlib` để đảm bảo tương thích đa nền tảng.
* **Xác thực mã vạch.** Sau khi lưu, bạn có thể đọc lại hình ảnh bằng `barcode.BarCodeReader` để xác nhận rằng văn bản đã mã hoá khớp với `extended_codetext`.
* **Mẹo hiệu năng.** Nếu bạn tạo nhiều mã vạch trong một vòng lặp, hãy tái sử dụng một thể hiện `BarCodeWriter` duy nhất và chỉ cập nhật `code_text` ở mỗi vòng lặp.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch Code 128** với dữ liệu ASCII và Unicode hỗn hợp và **lưu hình ảnh mã vạch** dưới dạng PNG bằng Aspose.BarCode trong Python. Script hoàn chỉnh bao gồm việc xây dựng codetext mở rộng, cấu hình writer, xuất ảnh, và kiểm tra phiên bản thư viện.

Từ đây bạn có thể khám phá:

* Thêm màu nền và màu chữ (`writer.back_color`, `writer.fore_color`).
* Nhúng mã vạch vào PDF bằng `Aspose.PDF`.
* Sử dụng lớp `BarCodeReader` để giải mã hình ảnh đã lưu và tự động xác minh nội dung.

Chúc lập trình vui vẻ, và hãy thoải mái thử nghiệm các biểu tượng và định dạng ảnh khác!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có ví dụ mã đầy đủ, hoạt động, kèm giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo mã vạch Code128 với Aspose.Barcode Python – Hướng dẫn đầy đủ](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [Cách tạo mã vạch trong Python – hướng dẫn chi tiết từng bước](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Cách tạo ảnh QR Code trong Python với Aspose.Barcode – Hướng dẫn đầy đủ](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}