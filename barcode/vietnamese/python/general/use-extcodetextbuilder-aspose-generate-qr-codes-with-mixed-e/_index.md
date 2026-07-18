---
category: general
date: 2026-07-18
description: Sử dụng extcodetextbuilder của Aspose để tạo mã QR kết hợp văn bản ASCII
  thuần và văn bản tiếng Nga UTF‑8. Tìm hiểu cách tạo mã QR bằng Aspose.Barcode trong
  Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- use extcodetextbuilder aspose
- Aspose.Barcode
- ECI encoding
- QR Code generation
- mixed codetext
language: vi
lastmod: 2026-07-18
og_description: Sử dụng ExtCodeTextBuilder của Aspose cho phép bạn pha trộn các đoạn
  văn bản thuần và được mã hoá UTF‑8 trong một mã QR. Hãy làm theo hướng dẫn chi tiết
  từng bước cho Aspose.Barcode trong Python.
og_image_alt: use extcodetextbuilder aspose QR code example showing mixed ECI text
og_title: sử dụng extcodetextbuilder aspose – Tạo mã QR với văn bản ECI hỗn hợp
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  headline: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  type: TechArticle
- description: use extcodetextbuilder aspose to create QR codes that combine plain
    ASCII and UTF‑8 Russian text. Learn Aspose.Barcode QR Code generation in Python.
  name: 'use extcodetextbuilder aspose: Generate QR Codes with Mixed ECI Text'
  steps:
  - name: What if my scanner doesn’t recognize the Cyrillic part?
    text: Make sure the scanning app advertises ECI support. Older hardware may ignore
      the ECI segment and treat the bytes as ISO‑8859‑1, resulting in garbled characters.
  - name: Can I add more than two fragments?
    text: Absolutely. Call `add_plain_codetext` or `add_eci_codetext` as many times
      as you need. The builder will concatenate them in the order you invoke the methods.
  - name: How do I change the QR Code size or foreground color?
    text: 'Use the `qr_generator.parameters` object:'
  - name: Is there a way to embed binary data (e.g., a small file) alongside text?
    text: Yes. Use `add_binary_codetext` with a byte array, and pair it with an appropriate
      ECI if the binary represents a specific character set. The builder will handle
      the necessary mode switches.
  type: HowTo
tags:
- barcode
- Aspose
- Python
- QR Code
- ECI
title: 'Sử dụng extcodetextbuilder aspose: Tạo mã QR với văn bản ECI hỗn hợp'
url: /vi/python/general/use-extcodetextbuilder-aspose-generate-qr-codes-with-mixed-e/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# sử dụng extcodetextbuilder aspose – Tạo QR Code với Văn bản ECI hỗn hợp

Bạn đã bao giờ tự hỏi làm thế nào **use extcodetextbuilder aspose** để nhúng cả ký tự tiếng Anh thuần túy và Cyrillic vào một QR Code duy nhất chưa? Bạn không phải là người duy nhất. Nhiều nhà phát triển gặp khó khăn khi cần pha trộn dữ liệu ASCII và không‑ASCII, đặc biệt khi máy quét mục tiêu yêu cầu các dấu hiệu ECI (Extended Channel Interpretation) đúng.  

Trong hướng dẫn này, chúng ta sẽ đi qua các bước chi tiết để tạo một QR Code chứa “HELLO123” **và** từ tiếng Nga “Привет”, toàn bộ bằng API Python của Aspose.Barcode. Khi kết thúc, bạn sẽ có một script sẵn sàng chạy, hiểu vì sao mỗi lời gọi lại quan trọng, và biết cách điều chỉnh quy trình cho các ngôn ngữ hoặc định dạng dữ liệu khác.

## Những gì bạn sẽ học

- Cách **khởi tạo ExtCodetextBuilder** và thêm các đoạn văn bản thường + đoạn mã ECI.  
- Tại sao giá trị **ECI encoding** `3` tương ứng với UTF‑8 và ảnh hưởng của nó tới việc quét.  
- Trình tự chính xác để thiết lập **bộ tạo QR Code** với Aspose.Barcode.  
- Cách lưu hình ảnh kết quả và xác minh nội dung hỗn hợp.  

**Yêu cầu trước** – bạn cần Python 3.8+, gói `aspose-barcode` đã được cài đặt (`pip install aspose-barcode`), và một thư mục có thể ghi ảnh vào. Không cần gì khác.

---

## use extcodetextbuilder aspose to build mixed codetext

Điều đầu tiên chúng ta cần là một thể hiện `ExtCodetextBuilder`. Hãy nghĩ nó như một mẫu builder nối các đoạn văn bản khác nhau trong khi tự động chèn các dấu hiệu ECI thích hợp phía sau.

```python
# Step 1: Build an extended codetext that mixes plain and ECI‑encoded fragments
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

# Create the builder object
ext_builder = ExtCodetextBuilder()

# Add plain ASCII text – this part needs no special handling
ext_builder.add_plain_codetext("HELLO123")                     # Plain ASCII text

# Add UTF‑8 encoded Russian text – ECI value 3 signals UTF‑8 to the scanner
ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")  # UTF‑8 encoded Russian text

# Retrieve the combined string that Aspose.Barcode will consume
extended_codetext = ext_builder.get_extended_codetext()
```

**Tại sao điều này quan trọng:**  
- `add_plain_codetext` giữ dữ liệu nguyên trạng, rất phù hợp cho số hoặc chữ cái tiếng Anh.  
- `add_eci_codetext` chèn một đoạn ECI (`[ECI:3]`) trước chuỗi được cung cấp, thông báo cho bất kỳ máy đọc nào tuân thủ rằng các byte tiếp theo là UTF‑8. Nếu không có đoạn này, máy quét sẽ hiểu các byte Cyrillic là rác.

> **Mẹo chuyên nghiệp:** Nếu bạn cần bộ ký tự khác, thay đổi giá trị `eci_encoding` theo bảng ECI (ví dụ, `26` cho ISO‑8859‑1).  

---

## Initialise QR Code generation with Aspose.Barcode

Bây giờ chúng ta đã có `extended_codetext` được định dạng đúng, có thể chuyển nó cho bộ tạo QR Code. Aspose.Barcode trừu tượng hoá việc tạo ma trận QR cấp thấp, cho phép bạn tập trung vào dữ liệu.

```python
# Step 2: Initialise a QR Code generator
qr_generator = BarcodeGenerator()
qr_generator.set_symbology(Symbology.QR)   # Choose QR as the symbology
```

**Điều gì đang diễn ra ở đây?**  
- `BarcodeGenerator()` tạo một đối tượng generator mới với các thiết lập mặc định (kích thước, độ phân giải, v.v.).  
- `set_symbology` thông báo cho engine rằng chúng ta muốn một QR Code thay vì, ví dụ, Code128.  

Nếu bạn cần mức độ sửa lỗi cao hơn, có thể gọi `qr_generator.parameters.barcode.qr_error_level = ...` trước khi gán codetext.

---

## Assign the extended codetext to the QR generator

Với generator đã sẵn sàng, bước tiếp theo chỉ đơn giản là cung cấp chuỗi hỗn hợp mà chúng ta đã xây dựng trước đó.

```python
# Step 3: Assign the extended codetext to the generator
qr_generator.set_extended_codetext(extended_codetext)
```

**Tại sao không dùng `set_codetext`?**  
`set_codetext` xử lý đầu vào như văn bản thuần, loại bỏ mọi dấu hiệu ECI. `set_extended_codetext` giữ nguyên các byte thô, bao gồm cả đoạn ECI, đảm bảo máy quét nhận được sự chuyển đổi ngôn ngữ đúng.

---

## Save the QR Code image and verify the result

Cuối cùng, chúng ta ghi QR Code ra đĩa. Aspose.Barcode hỗ trợ PNG, JPEG, BMP và nhiều định dạng khác; PNG là lựa chọn an toàn vì nó giữ dữ liệu không mất mát.

```python
# Step 4: Save the generated QR Code image
qr_generator.save("YOUR_DIRECTORY/qr_extended.png")
```

Bây giờ bạn sẽ có một file PNG tại vị trí đã chỉ định. Mở nó bằng bất kỳ ứng dụng quét QR nào hỗ trợ ECI (hầu hết smartphone hiện đại đều có). Quét một lần – bạn sẽ thấy “HELLO123”. Quét lại (hoặc dùng máy quét hiển thị dữ liệu thô) – bạn cũng sẽ nhận được “Привет”. Hai phần xuất hiện như một payload duy nhất, chính xác như chúng ta đã xây dựng.

![use extcodetextbuilder aspose QR code example](YOUR_DIRECTORY/qr_extended.png)

*Image alt text: use extcodetextbuilder aspose QR code example showing mixed ECI text*

---

## Full, Ready‑to‑Run Script

Kết hợp mọi thứ lại, đây là chương trình hoàn chỉnh mà bạn có thể sao chép‑dán vào một file tên `qr_mixed_eci.py`:

```python
from aspose.barcode import BarcodeGenerator, Symbology
from aspose.barcode.generation import ExtCodetextBuilder

def generate_mixed_eci_qr(output_path: str):
    # Build mixed codetext
    ext_builder = ExtCodetextBuilder()
    ext_builder.add_plain_codetext("HELLO123")
    ext_builder.add_eci_codetext(eci_encoding=3, codetext="Привет")
    extended_codetext = ext_builder.get_extended_codetext()

    # Initialise QR generator
    qr_generator = BarcodeGenerator()
    qr_generator.set_symbology(Symbology.QR)

    # Assign extended codetext
    qr_generator.set_extended_codetext(extended_codetext)

    # Save image
    qr_generator.save(output_path)
    print(f"QR Code saved to {output_path}")

if __name__ == "__main__":
    generate_mixed_eci_qr("qr_extended.png")
```

Chạy nó bằng:

```bash
python qr_mixed_eci.py
```

Bạn sẽ thấy một thông báo trên console xác nhận vị trí lưu, và file PNG sẽ xuất hiện ngay tại nơi bạn đã chỉ định.

---

## Common Questions & Edge Cases

### Nếu máy quét của tôi không nhận dạng được phần Cyrillic thì sao?
Đảm bảo ứng dụng quét của bạn công bố hỗ trợ ECI. Phần cứng cũ có thể bỏ qua đoạn ECI và xử lý các byte như ISO‑8859‑1, dẫn đến ký tự bị rối.

### Tôi có thể thêm hơn hai đoạn không?
Chắc chắn. Gọi `add_plain_codetext` hoặc `add_eci_codetext` bao nhiêu lần tùy thích. Builder sẽ nối chúng theo thứ tự bạn gọi các phương thức.

### Làm sao thay đổi kích thước QR Code hoặc màu nền?
Sử dụng đối tượng `qr_generator.parameters`:

```python
qr_generator.parameters.barcode.x_dimension = 4   # module size in points
qr_generator.parameters.barcode.qr_error_level = qr_generator.parameters.barcode.QrErrorLevel.QR_ECLEVEL_Q
qr_generator.save("qr_custom.png", BarCodeImageFormat.PNG, 300)  # 300 DPI
```

### Có cách nào nhúng dữ liệu nhị phân (ví dụ, một tệp nhỏ) cùng với văn bản không?
Có. Dùng `add_binary_codetext` với một mảng byte, và ghép nó với ECI thích hợp nếu dữ liệu nhị phân đại diện cho một bộ ký tự cụ thể. Builder sẽ xử lý các chuyển đổi chế độ cần thiết.

---

## Kết luận

Bây giờ bạn đã biết **cách sử dụng extcodetextbuilder aspose** để tạo QR Code kết hợp mượt mà giữa văn bản ASCII thuần và văn bản tiếng Nga mã hoá UTF‑8. Bằng cách tận dụng `ExtCodetextBuilder`, thiết lập **ECI encoding** đúng, và đưa kết quả vào **bộ tạo QR Code Aspose.Barcode**, bạn sẽ có một hình ảnh duy nhất, tuân thủ tiêu chuẩn, hoạt động trên các máy quét hiện đại.  

Từ đây, hãy thử thay `eci_encoding=3` bằng các định danh ngôn ngữ khác, hoặc thử nghiệm thêm các đoạn văn bản thuần để xây dựng payload đa ngôn ngữ. Bạn cũng có thể khám phá các tùy chọn `BarCodeImageFormat` để xuất SVG hoặc PDF nếu cần đồ họa vector.  

Chúc lập trình vui vẻ, và đừng ngại để lại bình luận nếu gặp bất kỳ khó khăn nào—phản hồi của bạn giúp cải thiện các hướng dẫn này!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây liên quan chặt chẽ và mở rộng các kỹ thuật đã trình bày trong bài viết này. Mỗi tài nguyên đều bao gồm mã mẫu đầy đủ và giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Generate Barcode Java - Set Code Text using Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)
- [Create barcode aspose .net - Configuring DataMatrix Code Text](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Aztec Code Text Encoding with Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-code-text-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}