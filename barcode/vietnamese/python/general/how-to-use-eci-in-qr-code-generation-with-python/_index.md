---
category: general
date: 2026-11-20
description: Học cách sử dụng ECI, tạo mã QR từ văn bản, xóa builder và lưu ảnh QR
  bằng thư viện barcode của Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to use eci
- generate qr from text
- how to clear builder
- save qr image
- clear qr builder
language: vi
lastmod: 2026-11-20
og_description: Cách sử dụng ECI để tạo QR từ văn bản, xóa trình tạo QR và lưu ảnh
  QR – hướng dẫn chi tiết từng bước.
og_image_alt: Diagram illustrating how to use ECI to generate a QR code and save the
  QR image
og_title: Cách sử dụng ECI trong việc tạo mã QR bằng Python
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to use ECI, generate QR from text, clear the builder, and
    save QR image using the Python barcode library.
  headline: How to use ECI in QR code generation with Python
  type: TechArticle
tags:
- QR code
- Python
- barcode
- ECI
title: Cách sử dụng ECI trong việc tạo mã QR bằng Python
url: /vi/python/general/how-to-use-eci-in-qr-code-generation-with-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách sử dụng ECI trong việc tạo mã QR bằng Python

Nếu bạn cần **cách sử dụng eci** khi tạo mã QR, hướng dẫn này sẽ chỉ ra các bước chính xác. Bạn sẽ thấy cách tạo QR từ văn bản, xóa bộ xây dựng, và cuối cùng lưu hình ảnh QR—tất cả chỉ với vài dòng Python.

Mã QR chứa dữ liệu đa ngôn ngữ thường yêu cầu một đoạn Extended Channel Interpretation (ECI) để máy quét biết bộ ký tự nào cần áp dụng. Hướng dẫn này sẽ chỉ bạn cách xây dựng codetext mở rộng, xóa builder khi tái sử dụng, và lưu kết quả dưới dạng file PNG.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- Python 3.8+ đã được cài đặt.
- Gói Aspose.BarCode cho Python qua .NET (hoặc bất kỳ thư viện `barcode` tương thích nào cung cấp `ExtCodetextBuilder` và `BarcodeGenerator`).
- Kiến thức cơ bản về các khái niệm mã QR.

Cài đặt thư viện bằng pip:

```bash
pip install aspose-barcode
```

> **Mẹo chuyên nghiệp:** Sử dụng môi trường ảo để tránh xung đột phiên bản.

## Bước 1: Nhập các lớp cần thiết

Các lớp chính bạn sẽ làm việc là `ExtCodetextBuilder` để xây dựng codetext mở rộng và `BarcodeGenerator` để tạo mã QR.

```python
from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
```

Các import này cho phép bạn truy cập các phương thức của builder (`add_plain_codetext`, `add_eci_codetext`, v.v.) và các hàm `set_code_text`, `set_symbology`, và `save` của generator.

## Bước 2: Tạo và cấu hình ExtCodetextBuilder

Tạo một instance builder mới là ví dụ cụ thể đầu tiên của **cách sử dụng eci**. Bạn cũng có thể xóa builder sau này nếu cần tái sử dụng.

```python
# Create an ExtCodetextBuilder instance
extended_text_builder = ExtCodetextBuilder()

# Optional: clear any previous items (useful when reusing the same builder)
extended_text_builder.clear()   # this demonstrates how to clear builder
```

Gọi `clear()` đảm bảo builder bắt đầu ở trạng thái sạch, điều này rất quan trọng khi tạo nhiều mã QR trong một vòng lặp.

## Bước 3: Thêm codetext thường (không‑ECI)

Văn bản thường không cần đoạn ECI. Sử dụng `add_plain_codetext` cho các chuỗi tương thích ASCII.

```python
# Add plain codetext (e.g., an English phrase)
extended_text_builder.add_plain_codetext("HelloWorld")
```

Builder hiện đang chứa đoạn thường `"HelloWorld"`.

## Bước 4: Thêm đoạn mã hoá ECI

Đây là phần cốt lõi của **cách sử dụng eci**: bạn chỉ định giá trị ECI (26 cho UTF‑8) và cung cấp chuỗi Unicode muốn mã hoá. Điều này cho phép mã QR chứa tiếng Nga, tiếng Trung, hoặc bất kỳ ngôn ngữ nào khác không được bao phủ bởi bộ ISO‑8859‑1 mặc định.

```python
# Add ECI‑encoded codetext (ECI value 26 = UTF‑8, Russian “Hello”)
extended_text_builder.add_eci_codetext(26, "Привет")
```

> **Tại sao điều này quan trọng:** Nếu không có chỉ báo ECI, máy quét sẽ giải mã các byte bằng bộ ký tự mặc định và hiển thị ký tự rối cho văn bản không phải ASCII.

## Bước 5: Lấy chuỗi codetext mở rộng đã kết hợp

Sau khi thêm tất cả các đoạn cần thiết, lấy chuỗi cuối cùng sẽ được truyền cho trình tạo QR.

```python
combined_extended_text = extended_text_builder.get_extended_codetext()
print("Extended codetext:", combined_extended_text)
```

Giá trị in ra trông giống như:

```
Extended codetext: [ECI26]ПриветHelloWorld
```

Định dạng chính xác phụ thuộc vào thư viện, nhưng phần quan trọng là dấu hiệu ECI (`[ECI26]`) đứng trước payload UTF‑8.

## Bước 6: Tạo mã QR bằng văn bản đã kết hợp

Bây giờ bạn có thể **tạo QR từ văn bản** bằng cách truyền codetext mở rộng cho `BarcodeGenerator`.

```python
# Initialize the QR generator
qr_generator = barcode.generation.BarcodeGenerator()

# Assign the combined extended codetext
qr_generator.set_code_text(combined_extended_text)

# Choose QR symbology (the library supports many, QR is the most common)
qr_generator.set_symbology(barcode.Symbology.QR)

# Save the QR image to disk – this demonstrates how to save QR image
output_path = "qr_extended.png"
qr_generator.save(output_path)

print(f"QR code saved to {output_path}")
```

Khi mở `qr_extended.png`, một mã QR xuất hiện, mã hoá cả chuỗi tiếng Anh thường và lời chào tiếng Nga. Quét nó bằng máy quét QR hiện đại sẽ hiển thị đúng “HelloWorld” và “Привет”.

### Tại sao bạn nên gọi `clear()` trước khi tái sử dụng builder

Nếu bạn tạo nhiều mã QR trong một vòng lặp, quên gọi `clear()` sẽ nối các đoạn cũ với đoạn mới, tạo ra mã không hợp lệ. Dưới đây là một mẫu nhanh:

```python
for text, eci, unicode_str in data_set:
    extended_text_builder.clear()                       # ensures a fresh start
    extended_text_builder.add_plain_codetext(text)
    extended_text_builder.add_eci_codetext(eci, unicode_str)
    qr_generator.set_code_text(extended_text_builder.get_extended_codetext())
    qr_generator.save(f"qr_{text}.png")
```

Đoạn mã này minh họa **cách xóa builder** và **cách tạo QR từ văn bản** lặp lại.

## Các trường hợp đặc biệt và lỗi thường gặp

| Tình huống | Điều cần chú ý | Cách xử lý |
|-----------|-------------------|---------------|
| **Giá trị ECI không hỗ trợ** | Thư viện ném ra `InvalidArgumentException`. | Chỉ sử dụng các giá trị ECI được liệt kê trong đặc tả (ví dụ, 26 cho UTF‑8, 20 cho Shift‑JIS). |
| **Văn bản kết hợp quá dài** | Phiên bản QR có thể vượt quá dung lượng tối đa. | Tăng phiên bản QR tự động (`qr_generator.set_qr_version(QRVersion.AUTO)`) hoặc chia dữ liệu thành nhiều mã QR. |
| **Lỗi quyền truy cập hệ thống tập tin** | `save` thất bại với `IOError`. | Đảm bảo thư mục đích tồn tại và tiến trình có quyền ghi. |
| **Hiển thị charset không đúng** | Máy quét hiển thị ký tự rối. | Xác minh giá trị ECI đúng khớp với mã hoá thực tế của chuỗi. |

## Ví dụ đầy đủ có thể chạy

Dưới đây là một script tự chứa mà bạn có thể sao chép, dán và chạy. Nó bao gồm tất cả các import, xử lý lỗi, và chú thích để rõ ràng.

```python
# qr_eci_example.py
# Demonstrates how to use ECI, generate QR from text, clear the builder,
# and save QR image using Aspose.BarCode for Python.

from aspose.barcode import barcode
from aspose.barcode.generation import ExtCodetextBuilder
import os

def generate_qr(plain_text: str, eci_value: int, unicode_text: str, out_file: str):
    """
    Creates a QR code that contains both plain and ECI‑encoded text.
    Parameters:
        plain_text – ASCII‑compatible string.
        eci_value  – Numeric ECI identifier (e.g., 26 for UTF‑8).
        unicode_text – Text that requires the specified ECI.
        out_file – Destination file path for the PNG image.
    """
    # Step 1: instantiate and clear the builder
    builder = ExtCodetextBuilder()
    builder.clear()                       # how to clear builder

    # Step 2: add segments
    builder.add_plain_codetext(plain_text)
    builder.add_eci_codetext(eci_value, unicode_text)

    # Step 3: retrieve combined text
    combined = builder.get_extended_codetext()
    print("Combined extended codetext:", combined)

    # Step 4: generate QR code
    generator = barcode.generation.BarcodeGenerator()
    generator.set_code_text(combined)
    generator.set_symbology(barcode.Symbology.QR)

    # Ensure output directory exists
    os.makedirs(os.path.dirname(out_file), exist_ok=True)

    # Step 5: save QR image – how to save QR image
    generator.save(out_file)
    print(f"QR code saved as {out_file}")

if __name__ == "__main__":
    # Example usage
    generate_qr(
        plain_text="HelloWorld",
        eci_value=26,               # UTF‑8
        unicode_text="Привет",      # Russian "Hello"
        out_file="output/qr_extended.png"
    )
```

Chạy script này sẽ tạo ra `output/qr_extended.png`, một mã QR mã hoá đúng cả văn bản tiếng Anh và tiếng Nga.

## Kết luận

Bạn giờ đã biết **cách sử dụng eci** khi xây dựng mã QR, cách **xóa builder QR** trước khi tái sử dụng, cách **tạo QR từ văn bản**, và các bước chính xác để **lưu ảnh QR** bằng Python. Bằng cách theo mẫu trên, bạn có thể nhúng bất kỳ chuỗi Unicode nào vào mã QR trong khi giữ trạng thái builder dự đoán được.

### Tiếp theo?

- Khám phá các giá trị ECI khác cho các ngôn ngữ như tiếng Trung (ECI 20) hoặc ISO‑8859‑5.
- Điều chỉnh mức độ sửa lỗi (`qr_generator.set_error_correction_level`) để cải thiện độ tin cậy khi quét.
- Kết hợp nhiều đoạn ECI trong một mã QR cho các tin nhắn đa ngôn ngữ.

Chúc bạn lập trình vui vẻ và tận hưởng việc tạo các mã QR đa ngôn ngữ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch với ECI bằng Aspose.Barcode Python](/barcode/english/python/general/how-to-generate-barcode-with-eci-using-aspose-barcode-python/)
- [Cách tạo ảnh mã QR trong Python với Aspose.Barcode – Hướng dẫn đầy đủ](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)
- [Cách tạo mã vạch trong Python – hướng dẫn chi tiết từng bước](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}