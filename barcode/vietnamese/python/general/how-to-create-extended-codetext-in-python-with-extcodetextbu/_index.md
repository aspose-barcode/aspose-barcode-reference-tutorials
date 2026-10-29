---
category: general
date: 2026-10-28
description: Học cách tạo extended codetext trong Python bằng ExtCodetextBuilder.
  Bao gồm dữ liệu thuần và dữ liệu được mã hoá ECI, mã từng bước và các mẹo thực hành
  tốt nhất.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create extended codetext
- ExtCodetextBuilder Python
- add plain codetext
- add eci codetext
- extended‑codetext example
language: vi
lastmod: 2026-10-28
og_description: Tạo extended codetext trong Python với ExtCodetextBuilder. Hướng dẫn
  này trình bày cách xử lý dữ liệu thường và dữ liệu được mã hoá ECI, mã nguồn đầy
  đủ có thể chạy và các lỗi thường gặp.
og_image_alt: Diagram showing how to create extended codetext using ExtCodetextBuilder
  in Python
og_title: Tạo đoạn mã mở rộng trong Python – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  headline: How to create extended codetext in Python with ExtCodetextBuilder
  type: TechArticle
- description: Learn how to create extended codetext in Python using ExtCodetextBuilder.
    Includes plain and ECI‑encoded data, step‑by‑step code and best‑practice tips.
  name: How to create extended codetext in Python with ExtCodetextBuilder
  steps:
  - name: Prerequisites
    text: '* Python 3.8 or newer. * The `extcodetext` package (or a similar library
      that provides `ExtCodetextBuilder`). Install it with:'
  - name: Handling other encodings
    text: 'If you need ISO‑8859‑1 (Western European) you would use `add_eci_codetext(4,
      "¡Hola!")`. For Shift‑JIS (Japanese) the ECI value is 20:'
  - name: 'Edge case: Empty strings'
    text: Calling `add_plain_codetext("")` or `add_eci_codetext(3, "")` is harmless;
      the builder simply ignores the empty fragment. However, repeated empty calls
      can lead to unnecessary ECI markers. Guard against this by checking string length
      before adding.
  type: HowTo
tags:
- Python
- encoding
- data‑serialization
title: Cách tạo extended codetext trong Python với ExtCodetextBuilder
url: /vi/python/general/how-to-create-extended-codetext-in-python-with-extcodetextbu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo extended codetext trong Python với ExtCodetextBuilder

Nếu bạn cần **tạo extended codetext** cho các ứng dụng barcode hoặc data‑matrix, hướng dẫn này sẽ chỉ cho bạn cách thực hiện trong Python. Bạn sẽ thấy cách kết hợp văn bản thường, thêm các phần ECI (Extended Channel Interpretation) cho ký tự Unicode, và lấy một chuỗi duy nhất, được định dạng đúng sẵn sàng để mã hoá.

Hướng dẫn bao gồm mọi thứ từ cài đặt thư viện cần thiết đến xử lý các trường hợp biên như giá trị ECI không được hỗ trợ. Khi hoàn thành, bạn sẽ có một mẫu có thể tái sử dụng và chèn vào bất kỳ dự án nào cần **tạo extended codetext**.

## Những gì bạn sẽ học

* Vai trò của `ExtCodetextBuilder` khi xây dựng các chuỗi mixed‑encoding.  
* Cách **thêm plain codetext** và **thêm ECI codetext** trong một thể hiện builder.  
* Cách xác minh đầu ra cuối cùng và khắc phục các lỗi thường gặp.  
* Các biến thể cho các bộ ký tự khác (ví dụ, ISO‑8859‑1, Shift‑JIS).  

### Yêu cầu trước

* Python 3.8 hoặc mới hơn.  
* Gói `extcodetext` (hoặc một thư viện tương tự cung cấp `ExtCodetextBuilder`). Cài đặt bằng:

```bash
pip install extcodetext
```

* Kiến thức cơ bản về Unicode và các giá trị ECI – ECI 3 tương ứng với UTF‑8, ECI 4 với ISO‑8859‑1, v.v.

> **Mẹo:** Giữ một bảng tham chiếu các số ECI gần tay. Điều này ngăn ngừa việc không khớp ngẫu nhiên giữa mã hoá đã khai báo và chuỗi byte thực tế.

## Hiểu về ExtCodetextBuilder

`ExtCodetextBuilder` là một tiện ích nhỏ nối nhiều đoạn văn bản lại với nhau đồng thời tự động chèn các dấu ECI cần thiết. Dấu ECI cho bộ mã hoá barcode phía dưới biết phải dùng bộ ký tự nào cho các byte tiếp theo. Nếu không có dấu này, các ký tự không phải ASCII sẽ bị hiểu sai.

Builder hoạt động theo ba giai đoạn đơn giản:

1. **Create** thể hiện builder.  
2. **Append** các đoạn plain hoặc đã mã hoá bằng ECI.  
3. **Retrieve** chuỗi extended‑codetext đã kết hợp.

Dưới đây chúng ta sẽ đi qua từng giai đoạn với mã cụ thể.

## Bước 1: Tạo một thể hiện ExtCodetextBuilder

Dòng đầu tiên khởi tạo đối tượng sẽ chứa tất cả các đoạn. Không cần cấu hình gì ở bước này.

```python
from extcodetext import ExtCodetextBuilder

# Step 1: Create an ExtCodetextBuilder instance
codetext_builder = ExtCodetextBuilder()
```

*Why this matters*: Khi khởi tạo builder, một bộ đệm nội bộ được cấp phát. Tất cả các lời gọi `add_*` sau này sẽ hoạt động trên bộ đệm đó, đảm bảo thứ tự bạn chỉ định.

## Bước 2: Thêm dữ liệu plain (không mã hoá)

Dữ liệu plain gồm các ký tự thuộc bộ ký tự mặc định (thường là ASCII). Dùng `add_plain_codetext` cho các đoạn này.

```python
# Step 2: Append plain (un‑encoded) data to the builder
codetext_builder.add_plain_codetext("ABC123")
```

*Explanation*: Chuỗi `"ABC123"` chỉ chứa các ký tự ASCII, vì vậy không cần dấu ECI. Phương thức chỉ đơn giản nối các byte thô vào bộ đệm nội bộ.

## Bước 3: Thêm dữ liệu cần có ECI trước

Khi bạn cần nhúng các ký tự Unicode—như Cyrillic, Japanese, hoặc emoji—bạn phải cho encoder biết bộ ký tự nào sẽ dùng. Điều này thực hiện bằng `add_eci_codetext(eci, text)`. Tham số đầu tiên là giá trị số ECI; tham số thứ hai là văn bản thực tế.

```python
# Step 3: Append data that must be preceded by an ECI (e.g., 3 for UTF‑8)
# This ensures the text "Привет" is correctly interpreted as UTF‑8
codetext_builder.add_eci_codetext(3, "Привет")
```

*Why ECI 3*: Theo tiêu chuẩn ISO/IEC 18004, ECI 3 ánh xạ tới UTF‑8. Khi chèn dấu này, máy đọc barcode sẽ biết giải mã các byte tiếp theo dưới dạng UTF‑8, bảo toàn các ký tự Cyrillic.

### Xử lý các mã hoá khác

Nếu bạn cần ISO‑8859‑1 (Western European) thì dùng `add_eci_codetext(4, "¡Hola!")`. Đối với Shift‑JIS (Japanese) giá trị ECI là 20:

```python
codetext_builder.add_eci_codetext(20, "こんにちは")
```

Luôn xác minh thư viện barcode mục tiêu hỗ trợ giá trị ECI đã chọn; các ECI không được hỗ trợ sẽ gây lỗi mã hoá.

## Bước 4: Lấy chuỗi extended‑codetext đã kết hợp

Sau khi đã thêm tất cả các đoạn, gọi `get_extended_codetext()` để nhận chuỗi cuối cùng. Chuỗi này bao gồm bất kỳ chuỗi escape ECI cần thiết nào.

```python
# Step 4: Retrieve the combined extended‑codetext string
extended_codetext = codetext_builder.get_extended_codetext()

print("Extended codetext:", extended_codetext)
```

**Kết quả mong đợi** (hiển thị dưới dạng Python `repr` để rõ ràng):

```
Extended codetext: 'ABC123\x1B\x1D\x03Привет'
```

*Breakdown*:

* `ABC123` – đoạn ASCII plain.  
* `\x1B\x1D\x03` – chuỗi escape ECI cho UTF‑8 (ESC GS 0x03).  
* `Привет` – từ Cyrillic được mã hoá UTF‑8.

Các byte escape cụ thể có thể khác nhau tùy vào triển khai thư viện, nhưng thứ tự logic luôn là *plain → ECI marker → Unicode text*.

## Ví dụ đầy đủ có thể chạy

Kết hợp mọi thứ lại, đây là một script tự chứa mà bạn có thể sao chép‑dán vào file tên `create_extended_codetext.py` và chạy ngay.

```python
#!/usr/bin/env python3
"""
Create extended codetext in Python using ExtCodetextBuilder.
Demonstrates plain text, UTF‑8 ECI, and how to retrieve the final string.
"""

from extcodetext import ExtCodetextBuilder

def main() -> None:
    # 1️⃣ Create the builder
    builder = ExtCodetextBuilder()

    # 2️⃣ Add a plain ASCII segment
    builder.add_plain_codetext("ABC123")

    # 3️⃣ Add a UTF‑8 segment (ECI 3) containing Cyrillic characters
    builder.add_eci_codetext(3, "Привет")

    # 4️⃣ Retrieve and display the extended codetext
    result = builder.get_extended_codetext()
    print("Extended codetext:", result)

if __name__ == "__main__":
    main()
```

Chạy script sẽ in ra chuỗi đã kết hợp, sẵn sàng cho bất kỳ encoder barcode nào chấp nhận đầu vào extended‑codetext.

## Những lỗi thường gặp và cách tránh

| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|---|---|---|
| `UnicodeEncodeError` khi gọi `add_eci_codetext` | Cung cấp một chuỗi chứa các ký tự không thể biểu diễn trong ECI đã chọn | Xác minh ECI khớp với mã hoá thực tế của chuỗi (ví dụ, dùng ECI 3 cho bất kỳ văn bản UTF‑8 nào). |
| Thiếu dấu ECI trong đầu ra cuối cùng | Nhầm lẫn sử dụng `add_plain_codetext` cho dữ liệu không phải ASCII | Chuyển sang `add_eci_codetext` cho bất kỳ ký tự nào ngoài phạm vi ASCII. |
| Máy quét mã vạch hiển thị ký tự rối | Máy quét không hỗ trợ giá trị ECI đã chọn | Chọn một ECI được hỗ trợ rộng rãi (UTF‑8 được hỗ trợ rộng rãi) hoặc quay lại ISO‑8859‑1 nếu ngôn ngữ mục tiêu cho phép. |
| `get_extended_codetext` trả về chuỗi rỗng | Không có đoạn nào được thêm trước khi gọi phương thức | Đảm bảo ít nhất một lời gọi `add_*` được thực thi. |

### Trường hợp đặc biệt: Chuỗi rỗng

Gọi `add_plain_codetext("")` hoặc `add_eci_codetext(3, "")` không gây hại; builder sẽ bỏ qua đoạn rỗng. Tuy nhiên, việc gọi liên tục các đoạn rỗng có thể tạo ra các dấu ECI không cần thiết. Hãy kiểm tra độ dài chuỗi trước khi thêm.

```python
text = "data"
if text:
    builder.add_plain_codetext(text)
```

## Mở rộng mẫu cho dữ liệu động

Trong các ứng dụng thực tế, bạn thường xây dựng extended codetext từ đầu vào người dùng hoặc bản ghi trong cơ sở dữ liệu. Đoạn mã dưới đây cho thấy một vòng lặp xử lý danh sách các tuple `(type, value)`, trong đó `type` là `"plain"` hoặc `"eci"`.

```python
fragments = [
    ("plain", "Order#"),
    ("plain", "98765"),
    ("eci", (3, "商品")),   # Japanese word "商品" (product) encoded as UTF‑8
]

for kind, payload in fragments:
    if kind == "plain":
        builder.add_plain_codetext(payload)
    elif kind == "eci":
        eci_val, text = payload
        builder.add_eci_codetext(eci_val, text)
    else:
        raise ValueError(f"Unsupported fragment type: {kind}")

print(builder.get_extended_codetext())
```

Cách tiếp cận này mở rộng tốt: bạn có thể đọc định nghĩa các đoạn từ JSON, CSV, hoặc API mà không cần thay đổi logic xây dựng cốt lõi.

## Kiểm thử đầu ra

Một unit test nhanh giúp xác nhận builder hoạt động như mong đợi. Sử dụng `pytest`:

```python
def test_extended_codetext():
    b = ExtCodetextBuilder()
    b.add_plain_codetext("X")
    b.add_eci_codetext(3, "✓")   # Check mark in UTF‑8
    result = b.get_extended_codetext()
    assert result.startswith("X")
    assert "\x1B\x1D\x03".encode() in result.encode()
```

Chạy `pytest` nên thành công, xác nhận rằng dấu ECI xuất hiện đúng vị trí cần thiết.

## Các khái niệm liên quan bạn có thể khám phá tiếp theo

* **Thư viện mã hoá barcode** – ví dụ, `python-barcode`, `zxing` bindings, cho phép nhận trực tiếp chuỗi extended codetext.  
* **Tham chiếu bảng ECI** – danh sách đầy đủ các giá trị số ECI được công bố bởi ISO/IEC 18004 và có thể lưu dưới dạng dictionary Python để tra cứu.  
* **Mức độ sửa lỗi** – khi tạo mã QR, kết hợp extended codetext với mức sửa lỗi phù hợp (L, M, Q, H) để quét ổn định.  

## Kết luận

Bạn giờ đã biết cách **tạo extended codetext** trong Python bằng `ExtCodetextBuilder`. Quy trình rất đơn giản:

1. Khởi tạo builder.  
2. Thêm các đoạn plain và đã mã hoá bằng ECI theo nhu cầu.  
3. Lấy chuỗi cuối cùng và truyền cho trình tạo barcode của bạn.

Bằng cách theo mẫu trên, bạn có thể xử lý bất kỳ sự kết hợp nào của dữ liệu ASCII và Unicode, tránh các lỗi mã hoá phổ biến, và tạo ra các chuỗi sẵn sàng cho barcode hoạt động trên nhiều loại máy quét. Thử nghiệm với các ECI khác nhau, tích hợp builder vào pipeline dữ liệu của bạn, và bạn sẽ có nền tảng vững chắc cho mọi nhu cầu extended‑codetext.

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}