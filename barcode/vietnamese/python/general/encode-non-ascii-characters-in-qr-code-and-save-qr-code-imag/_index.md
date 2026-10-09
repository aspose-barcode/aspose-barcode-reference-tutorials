---
category: general
date: 2026-09-10
description: Mã hoá các ký tự không phải ASCII trong mã QR và lưu hình ảnh mã QR bằng
  một trình xây dựng Python đơn giản. Thực hiện theo hướng dẫn từng bước sử dụng ExtCodetextBuilder
  và BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- encode non ascii characters
- save qr code image
- extended codetext builder
- eci encoding python
- barcode generation python
language: vi
lastmod: 2026-09-10
og_description: Mã hoá các ký tự không phải ASCII trong mã QR và lưu hình ảnh mã QR
  bằng Python. Hướng dẫn này chỉ ra cách xây dựng văn bản mã mở rộng, tạo mã QR và
  lưu hình ảnh.
og_image_alt: Diagram showing encode non ASCII characters in QR code and save QR code
  image workflow
og_title: Mã hoá ký tự không phải ASCII trong mã QR và lưu ảnh mã QR – hướng dẫn Python
  từng bước
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Encode non ASCII characters in a QR code and save QR code image with
    a simple Python builder. Follow a step‑by‑step guide using ExtCodetextBuilder
    and BarcodeGenerator.
  headline: Encode non ASCII characters in QR code and save QR code image
  type: TechArticle
tags:
- barcode
- QR code
- Python
title: Mã hoá các ký tự không phải ASCII trong mã QR và lưu ảnh mã QR
url: /vi/python/general/encode-non-ascii-characters-in-qr-code-and-save-qr-code-imag/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Mã hoá ký tự không phải ASCII trong mã QR và lưu ảnh mã QR

Nếu bạn cần **mã hoá ký tự không phải ASCII** trong một mã QR, hướng dẫn này sẽ chỉ cho bạn cách thực hiện và sau đó **lưu ảnh mã QR** vào đĩa. Dù bạn đang xử lý dữ liệu tiếng Nga, tiếng Trung, hoặc emoji, ExtCodetextBuilder cho phép bạn kết hợp văn bản thường và các đoạn mã hoá ECI mà không cần can thiệp thủ công vào byte.

Bạn sẽ học cách tạo một chuỗi extended codetext, tạo một mã QR hiểu chuỗi đó, và cuối cùng ghi ảnh mã vạch vào tệp. Bài hướng dẫn giả định bạn có kiến thức cơ bản về Python và đã cài đặt SDK `barcode`.

## Yêu cầu trước

* Đã cài đặt Python 3.8+.
* Gói Python `barcode` (hoặc SDK tương ứng) cung cấp `ExtCodetextBuilder`, `CodetextEncodingType`, và `BarcodeGenerator`.
* Quyền ghi vào thư mục nơi bạn muốn **lưu ảnh mã QR**.

Bạn có thể cài đặt SDK bằng pip (thay `barcode-sdk` bằng tên gói thực tế):

```bash
pip install barcode-sdk
```

## Bước 1: Tạo một extended codetext builder

Bước đầu tiên là khởi tạo `ExtCodetextBuilder`. Đối tượng này thu thập nhiều đoạn văn bản và tạo ra một chuỗi duy nhất mà ký hiệu mã QR có thể hiểu.

```python
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Initialize the builder that will hold all text parts
ext_builder = ExtCodetextBuilder()
```

*​*Tại sao điều này quan trọng*​*: Mã QR hỗ trợ **extended codetext**, có nghĩa là bạn có thể nhúng nhiều chế độ mã hoá (plain, ECI, v.v.) trong một mã vạch. Builder trừu tượng hoá việc định dạng cấp thấp cần thiết theo chuẩn QR.

## Bước 2: Thêm một đoạn plain‑text

Plain text là chế độ mặc định và hoạt động cho các ký tự ASCII. Thêm nó đầu tiên cung cấp một dự phòng có thể đọc được cho các máy quét bỏ qua ECI.

```python
# Add simple ASCII text
ext_builder.add_plain_codetext("HelloWorld")
```

Nếu bạn bỏ qua bước này, mã QR sẽ chỉ chứa đoạn ECI, mà một số máy đọc cũ có thể không giải mã đúng.

## Bước 3: Thêm một đoạn ECI‑encoded cho các ký tự không phải ASCII

Để bao gồm các ký tự ngoài phạm vi ASCII—như Cyrillic, tiếng Trung, hoặc emoji—bạn phải chỉ định một mã hoá ECI (Extended Channel Interpretation). Ở đây chúng ta dùng UTF‑8 cho từ tiếng Nga “Привет”.

```python
# Add a UTF‑8 encoded segment containing non‑ASCII characters
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")  # Russian “Hi”
```

*​*Tại sao cách này hoạt động*​*: Chuẩn QR định nghĩa các giá trị ECI để thông báo cho máy quét bộ ký tự nào cần áp dụng. Nếu không có dấu hiệu ECI, các byte thô sẽ được hiểu là ISO‑8859‑1, dẫn đến kết quả rối mắt.

## Bước 4: Lấy chuỗi extended codetext đã kết hợp

Sau khi thêm tất cả các đoạn mong muốn, gọi `get_extended_codetext()` để lấy chuỗi cuối cùng mà trình tạo mã vạch mong đợi.

```python
# Combine all parts into one extended codetext string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)
```

Giá trị được in ra trông giống như một chuỗi các ký tự điều khiển theo sau là văn bản thực tế, nhưng bạn không bao giờ cần phải phân tích thủ công.

## Bước 5: Tạo mã QR bằng extended codetext

Bây giờ tạo một `BarcodeGenerator`, đặt ký hiệu thành QR (định dạng 2‑D duy nhất phổ biến hỗ trợ extended codetext), và cung cấp chuỗi đã kết hợp.

```python
# Initialize the QR generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)          # QR supports extended codetext
qr_generator.set_code_text(extended_codetext)
```

*​*Mẹo*​*: Nếu bạn thử cùng quy trình với Code‑128 hoặc DataMatrix, SDK sẽ ném ra ngoại lệ vì các định dạng đó không thể hiểu các dấu hiệu ECI.

## Bước 6: Lưu ảnh mã QR

Cuối cùng, ghi mã vạch vào tệp PNG. Đây là nơi bạn **lưu ảnh mã QR** để sử dụng sau.

```python
output_path = "output/qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Đảm bảo thư mục `output` tồn tại hoặc tạo nó bằng `os.makedirs('output', exist_ok=True)` trước khi gọi `save`.

### Ví dụ đầy đủ có thể chạy

Kết hợp tất cả các bước lại với nhau sẽ cho bạn một script tự chứa mà bạn có thể chạy ngay lập tức:

```python
import os
from barcode import ExtCodetextBuilder, CodetextEncodingType, BarcodeGenerator, Symbology

# Ensure the output directory exists
os.makedirs("output", exist_ok=True)

# 1️⃣ Create the builder
ext_builder = ExtCodetextBuilder()

# 2️⃣ Add plain ASCII text
ext_builder.add_plain_codetext("HelloWorld")

# 3️⃣ Add UTF‑8 encoded non‑ASCII text (Russian)
ext_builder.add_eci_codetext(CodetextEncodingType.UTF_8, "Привет")

# 4️⃣ Retrieve the combined string
extended_codetext = ext_builder.get_extended_codetext()
print("Extended codetext:", extended_codetext)

# 5️⃣ Generate QR code
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)
qr_generator.set_code_text(extended_codetext)

# 6️⃣ Save the image
output_file = "output/qr_extended.png"
qr_generator.save(output_file)
print(f"QR code saved to {output_file}")
```

**Kết quả mong đợi** (console):

```
Extended codetext: <binary representation showing ECI markers>
QR code saved to output/qr_extended.png
```

Mở `qr_extended.png` bằng bất kỳ máy quét QR nào sẽ hiển thị `HelloWorldПривет`. Các máy quét hiểu ECI sẽ hiển thị ký tự Cyrillic đúng; các máy khác sẽ chỉ hiển thị phần ASCII.

## Các câu hỏi thường gặp & trường hợp đặc biệt

| Question | Answer |
|----------|--------|
| *Tôi có thể sử dụng các mã hoá khác như Shift‑JIS không?* | Có. Thay `CodetextEncodingType.UTF_8` bằng `CodetextEncodingType.SHIFT_JIS` và cung cấp văn bản phù hợp. |
| *Nếu dữ liệu kết hợp vượt quá khả năng của QR thì sao?* | Mã QR có giới hạn phiên bản (tối đa 177 × 177 mô-đun). Nếu builder ném ngoại lệ kích thước, bạn có thể tăng mức sửa lỗi hoặc chia dữ liệu thành nhiều mã QR. |
| *Có cần đặt một phiên bản QR cụ thể không?* | SDK tự động chọn phiên bản nhỏ nhất phù hợp với dữ liệu. Bạn có thể ép buộc một phiên bản bằng `qr_generator.set_qr_version(10)` nếu cần. |
| *Ảnh sẽ trong suốt không?* | Mặc định SDK ghi PNG với nền trắng. Sử dụng `qr_generator.set_background_color(Color.Transparent)` trước `save` nếu bạn cần trong suốt. |

## Kết luận

Trong bài hướng dẫn này bạn đã học cách **mã hoá ký tự không phải ASCII** trong một mã QR bằng `ExtCodetextBuilder` và sau đó **lưu ảnh mã QR** bằng `BarcodeGenerator`. Quy trình bao gồm xây dựng một chuỗi extended codetext, thêm cả các đoạn plain và ECI‑encoded, tạo ký hiệu QR, và cuối cùng ghi tệp ảnh.

Từ đây bạn có thể khám phá:

* Thêm nhiều đoạn ECI (ngôn ngữ khác nhau hoặc emoji).
* Điều chỉnh mức sửa lỗi QR để tăng độ tin cậy.
* Nhúng PNG đã tạo vào PDF hoặc trang web.

Chúc lập trình vui vẻ, và tận hưởng việc tạo các mã QR đa ngôn ngữ!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ hoạt động với các giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Generate Code128 Barcode with Aspose.Barcode Python – Full Guide](/barcode/english/python/general/generate-code128-barcode-with-aspose-barcode-python-full-gui/)
- [display product name using Python barcode library – step‑by‑step guide](/barcode/english/python/general/display-product-name-using-python-barcode-library-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}