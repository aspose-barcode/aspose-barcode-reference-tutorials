---
category: general
date: 2026-11-27
description: Học cách tạo mã vạch có văn bản và tạo mã vạch hành tinh trong Python
  — hướng dẫn từng bước để xuất ra PNG độ phân giải cao.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with text
- how to generate barcode
- generate planet barcode
- Python barcode generation
- high‑resolution barcode PNG
language: vi
lastmod: 2026-11-27
og_description: Tạo mã vạch kèm văn bản và tạo mã vạch planet trong Python. Tham khảo
  hướng dẫn đầy đủ này để xuất ra PNG độ phân giải cao.
og_image_alt: Screenshot showing how to create barcode with text using the Planet
  barcode generator
og_title: Tạo mã vạch với văn bản trong Python – tạo mã vạch Planet dễ dàng
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to create barcode with text and generate planet barcode in
    Python—step‑by‑step guide for high‑resolution PNG output.
  headline: How to create barcode with text using the Planet format in Python
  type: TechArticle
tags:
- barcode
- Python
- Planet format
- image generation
title: Cách tạo mã vạch có văn bản bằng định dạng Planet trong Python
url: /vi/python-java/general/how-to-create-barcode-with-text-using-the-planet-format-in-p/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch có văn bản sử dụng định dạng Planet trong Python

Nếu bạn cần **tạo mã vạch có văn bản** cho hệ thống gửi thư, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chi tiết. Bạn sẽ thấy một ví dụ ngắn gọn, toàn diện tạo ra mã vạch Planet, điều chỉnh độ phân giải và lưu kết quả dưới dạng ảnh PNG.

Việc tạo mã vạch là yêu cầu phổ biến trong các ứng dụng logistics, quản lý tồn kho và bán vé. Trong hướng dẫn này, bạn sẽ không chỉ học **cách tạo file mã vạch** mà còn hiểu tại sao mỗi bước cấu hình lại quan trọng và cách tránh các lỗi thường gặp.

## Những gì bạn sẽ học

* Thiết lập trình tạo mã vạch Planet với văn bản tùy chỉnh.  
* Điều chỉnh kích thước X‑dimension để tăng độ nét của ảnh.  
* Lưu mã vạch dưới dạng file PNG có thể in hoặc hiển thị trên web.  
* Mở rộng ví dụ sang các loại mã vạch khác hoặc các định dạng đầu ra khác.

**Yêu cầu trước**

* Python 3.8 hoặc mới hơn.  
* Gói `aspose-barcode` (hoặc bất kỳ thư viện tương thích nào cung cấp `BarcodeGenerator`, `EncodeTypes` và `BarCodeImageFormat`).  
* Kiến thức cơ bản về lập trình Python.

Bạn có thể cài đặt gói cần thiết bằng:

```bash
pip install aspose-barcode
```

---

## Bước 1: Tạo mã vạch có văn bản – khởi tạo trình tạo

Điều đầu tiên bạn phải làm là tạo một thể hiện `BarcodeGenerator` biết sẽ sử dụng ký hiệu nào và mã hoá văn bản nào. Đối với mã vạch Planet, giá trị enum `EncodeTypes.Planet` thông báo cho thư viện tuân theo chuẩn USPS Planet.

```python
# Import the necessary classes from the Aspose.BarCode library
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1: Initialize the generator with the desired text
# The text "123456" will appear beneath the Planet barcode pattern.
gen = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

**Tại sao lại quan trọng:**  
Đối tượng `BarcodeGenerator` bao gồm tất cả các thiết lập cho mã vạch. Cung cấp văn bản ngay khi khởi tạo đảm bảo giá trị đã mã hoá không thay đổi trong suốt quá trình, tránh các sự không khớp không mong muốn.

---

## Bước 2: Điều chỉnh thiết lập – cách tạo mã vạch với độ phân giải cao hơn

Một mã vạch độ phân giải thấp có thể bị mờ khi in trên máy in nhãn. X‑dimension (độ rộng mô-đun) kiểm soát kích thước của mỗi thanh riêng lẻ. Đặt giá trị thành 4 pixel sẽ cho ra một ảnh sắc nét, độ phân giải cao, phù hợp với hầu hết các máy in hiện đại.

```python
# Step 2: Increase the X‑dimension to 4 pixels for better clarity
gen.parameters.barcode.x_dimension.pixels = 4
```

**Giải thích:**  
* `gen.parameters.barcode.x_dimension.pixels` trực tiếp ánh xạ tới độ rộng thực tế của một mô-đun.  
* Giá trị **4** nghĩa là mỗi thanh rộng bốn pixel, tương đương khoảng 0.127 mm ở 300 dpi—nằm trong khoảng khuyến nghị cho mã vạch USPS Planet.  

**Mẹo:** Nếu bạn cần DPI khác, tính độ rộng pixel tương ứng (ví dụ: 2 pixel cho 150 dpi, 8 pixel cho 600 dpi).

---

## Bước 3: Lưu ảnh – tạo mã vạch planet dưới dạng PNG

Khi trình tạo đã được cấu hình, bạn có thể render mã vạch ra file ảnh. PNG là định dạng không mất dữ liệu, đảm bảo mẫu mô-đun được giữ nguyên.

```python
# Step 3: Save the generated barcode as a PNG image
output_path = "output/PostalPlanetBarHeightNone.png"
gen.save(output_path, BarCodeImageFormat.Png)
print(f"Barcode saved to {output_path}")
```

**Kết quả:**  
Chạy script sẽ tạo một file có tên `PostalPlanetBarHeightNone.png` chứa mã vạch Planet mã hoá chuỗi “123456”. Kích thước ảnh sẽ khoảng 200 × 100 pixel, tùy thuộc vào X‑dimension bạn đã chọn.

---

## Tùy chọn: Kiểm tra mã vạch bằng mắt

Bạn có thể nhanh chóng mở file PNG vừa tạo bằng bất kỳ trình xem ảnh nào để xác nhận rằng mã vạch sắc nét và văn bản có thể đọc được xuất hiện dưới mẫu.

```python
from PIL import Image

img = Image.open(output_path)
img.show()
```

Nếu ảnh bị mờ, hãy quay lại **Bước 2** và tăng X‑dimension cho đến khi các thanh được xác định rõ ràng.

---

## Các biến thể phổ biến và trường hợp đặc biệt

| Tình huống | Điều chỉnh |
|-----------|------------|
| **Độ dài văn bản khác nhau** | Mã vạch Planet hỗ trợ tối đa 12 ký tự số. Nếu vượt quá, thư viện sẽ ném ngoại lệ. |
| **Định dạng đầu ra thay thế** | Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg` hoặc `BarCodeImageFormat.Bmp` cho các trường hợp sử dụng khác. |
| **Màu nền/màu tiền tố tùy chỉnh** | Dùng `gen.parameters.barcode.barcode_color = Color.Blue` và `gen.parameters.barcode.back_color = Color.White`. |
| **Không hiển thị văn bản người đọc** | Đặt `gen.parameters.barcode.hide_code_text = True` để tạo mã vạch không có chú thích phía dưới. |
| **Tạo hàng loạt** | Lặp qua danh sách các chuỗi, tạo một `BarcodeGenerator` mới cho mỗi chuỗi và lưu chúng vào các file có tên duy nhất. |

Các biến thể này cho phép bạn **tạo file mã vạch planet** phù hợp với nhiều yêu cầu kinh doanh khác nhau.

---

## Script đầy đủ – sẵn sàng chạy

Dưới đây là script hoàn chỉnh, tự chứa, bạn có thể sao chép, dán và thực thi. Nó bao gồm tất cả các import, xử lý lỗi và chú thích.

```python
"""
Complete example: create barcode with text and generate a Planet barcode PNG.
Author: Your Name
Date: 2026-11-27
"""

import os
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from aspose.barcode import Color  # optional, for color customization
from PIL import Image

def create_planet_barcode(text: str, output_dir: str, x_dim_pixels: int = 4) -> str:
    """
    Generates a Planet barcode with the given text and saves it as a PNG.
    
    Args:
        text: Numeric string to encode (max 12 characters for Planet).
        output_dir: Directory where the PNG will be stored.
        x_dim_pixels: Width of a single module in pixels (default 4 for high resolution).
    
    Returns:
        Full path to the saved PNG file.
    """
    if not text.isdigit():
        raise ValueError("Planet barcode requires numeric text only.")
    if len(text) > 12:
        raise ValueError("Planet barcode supports up to 12 digits.")
    
    # Ensure the output directory exists
    os.makedirs(output_dir, exist_ok=True)
    
    # Initialize the generator with the desired text
    gen = BarcodeGenerator(EncodeTypes.Planet, text)
    
    # Adjust resolution via X‑dimension
    gen.parameters.barcode.x_dimension.pixels = x_dim_pixels
    
    # Build the output file path
    file_name = f"Planet_{text}.png"
    full_path = os.path.join(output_dir, file_name)
    
    # Save as PNG
    gen.save(full_path, BarCodeImageFormat.Png)
    
    return full_path

if __name__ == "__main__":
    try:
        result_path = create_planet_barcode("123456", "output")
        print(f"Barcode successfully generated: {result_path}")
        
        # Open the image for a quick visual check
        Image.open(result_path).show()
    except Exception as e:
        print(f"Error: {e}")
```

**Giải thích script**

* Hàm `create_planet_barcode` gói ba bước chính, giúp mã dễ tái sử dụng.  
* Kiểm tra đầu vào đảm bảo bạn tuân theo quy chuẩn Planet (chỉ số, tối đa 12 chữ số).  
* Hàm tự động tạo thư mục đầu ra, vì vậy bạn không cần quản lý thư mục thủ công.  
* Sau khi tạo, script mở ảnh bằng Pillow (`PIL`) để kiểm tra ngay lập tức.

---

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch có văn bản** và **tạo file mã vạch planet** trong Python. Hướng dẫn đã đề cập đến khởi tạo, tinh chỉnh độ phân giải và xuất file, cùng với các tùy chỉnh tùy chọn và các trường hợp đặc biệt thường gặp.  

Từ đây, bạn có thể:

* Thay `EncodeTypes.Planet` bằng các ký hiệu khác (ví dụ: `EncodeTypes.Code128`) để tái sử dụng cùng mẫu.  
* Tích hợp hàm vào dịch vụ web trả về ảnh mã vạch theo yêu cầu.  
* Thử nghiệm xử lý hàng loạt để tạo hàng ngàn mã vạch cho chiến dịch gửi thư bulk.

Hãy tự do điều chỉnh script cho nhu cầu dự án của bạn và chia sẻ kết quả trong phần bình luận. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây liên quan chặt chẽ và mở rộng các kỹ thuật đã trình bày trong bài này. Mỗi tài nguyên đều bao gồm mã mẫu hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to generate barcode in Python – complete step‑by‑step guide](/barcode/english/python-java/general/how-to-generate-barcode-in-python-complete-step-by-step-guid/)
- [Create barcode PNG in Python – step‑by‑step guide](/barcode/english/python-java/general/create-barcode-png-in-python-step-by-step-guide/)
- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}