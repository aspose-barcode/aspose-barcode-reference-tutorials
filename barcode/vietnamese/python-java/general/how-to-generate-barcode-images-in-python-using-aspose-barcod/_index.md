---
category: general
date: 2026-11-23
description: Cách tạo hình ảnh mã vạch trong Python với Aspose.BarCode. Tìm hiểu cách
  tạo mã vạch Planet, điều chỉnh kích thước X và xuất ra PNG với các thanh trống.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- Python barcode generation
- Aspose.BarCode library
- Planet barcode symbology
- empty bars barcode
- barcode image PNG
language: vi
lastmod: 2026-11-23
og_description: Cách tạo mã vạch trong Python bằng Aspose.BarCode. Hướng dẫn này sẽ
  chỉ cho bạn cách tạo mã vạch Planet với các thanh trống và lưu nó dưới dạng PNG.
og_image_alt: Screenshot of Python code that generates a Planet barcode with empty
  bars saved as a PNG file
og_title: Cách tạo mã vạch trong Python – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  headline: How to generate barcode images in Python using Aspose.BarCode
  type: TechArticle
- description: How to generate barcode images in Python with Aspose.BarCode. Learn
    to create a Planet barcode, adjust X‑dimension, and output an empty‑bars PNG.
  name: How to generate barcode images in Python using Aspose.BarCode
  steps:
  - name: Switching to a different symbology
    text: 'If you need a QR code, Code 128, or any other format, replace `EncodeTypes.Planet`
      with the appropriate enum value:'
  - name: Changing the image format
    text: 'Aspose.BarCode supports PNG, JPEG, BMP, and TIFF. To generate a JPEG instead:'
  - name: Adjusting image size without losing quality
    text: 'You can control the overall image dimensions via the `resolution` property
      or by scaling the X‑dimension and Y‑dimension together. For high‑resolution
      prints, set a higher DPI:'
  - name: Handling long data strings
    text: 'The Planet symbology has a limited data capacity (up to 8 characters).
      If you try to encode a longer string, the generator raises an exception. Validate
      the length before creating the barcode:'
  type: HowTo
tags:
- barcode
- Python
- Aspose
title: Cách tạo hình ảnh mã vạch trong Python bằng Aspose.BarCode
url: /vi/python-java/general/how-to-generate-barcode-images-in-python-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo hình ảnh mã vạch trong Python bằng Aspose.BarCode

Việc tạo hình ảnh mã vạch trong Python rất đơn giản với thư viện Aspose.BarCode. Hướng dẫn này sẽ chỉ cho bạn từng bước cách tạo mã vạch sử dụng ký hiệu Planet, tùy chỉnh kích thước X và tạo file PNG kiểu thanh rỗng.

Bạn sẽ thấy một script hoàn chỉnh, có thể chạy được mà bạn có thể sao chép vào dự án của mình. Bài hướng dẫn cũng bao gồm các biến thể phổ biến—như chuyển sang ký hiệu khác hoặc định dạng đầu ra khác—để bạn có thể điều chỉnh giải pháp cho nhu cầu của mình.

## Yêu cầu trước

* Python 3.8 hoặc mới hơn đã được cài đặt.  
* Truy cập vào terminal hoặc command prompt.  
* Giấy phép Aspose.BarCode for Python đang hoạt động (phiên bản đánh giá miễn phí có thể dùng để thử nghiệm).  
* Kiến thức cơ bản về quản lý gói Python (`pip`).  

## Bước 1: Cài đặt gói Aspose.BarCode

Aspose phân phối API Python của mình qua PyPI. Cài đặt nó bằng trình quản lý gói tiêu chuẩn:

```bash
pip install asposebarcode
```

> **Mẹo chuyên nghiệp:** Sử dụng môi trường ảo (`python -m venv venv`) để giữ các phụ thuộc tách biệt với các dự án khác.

## Bước 2: Nhập các lớp Aspose.BarCode cần thiết

Câu lệnh import sẽ đưa vào generator, enumeration của các ký hiệu, và enum định dạng ảnh.

```python
from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

* `BarcodeGenerator` tạo đối tượng mã vạch.  
* `EncodeTypes` liệt kê tất cả các ký hiệu được hỗ trợ—ở đây chúng ta sẽ dùng `Planet`.  
* `BarCodeImageFormat` xác định loại file đầu ra (PNG, JPEG, v.v.).  

## Bước 3: Tạo generator mã vạch cho ký hiệu Planet

Khởi tạo generator với ký hiệu mong muốn và dữ liệu bạn muốn mã hoá.

```python
# Create a generator for the Planet symbology with the value "123456"
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")
```

Ký hiệu `Planet` tạo ra một mẫu vòng tròn, rất thích hợp cho mục đích trang trí hoặc thương hiệu.

## Bước 4: Điều chỉnh kích thước X (độ rộng module)

Kích thước X kiểm soát độ rộng của thanh nhỏ nhất (module). Đặt nó thành 4 pixel sẽ cho ra một hình ảnh rõ nét, độ phân giải cao.

```python
# Set the module width to 4 pixels
barcode.parameters.barcode.x_dimension.pixels = 4
```

Thay đổi kích thước X hữu ích khi bạn cần một mã vạch có thể phóng to/thu nhỏ tốt cho việc in ấn hoặc hiển thị trên màn hình.

## Bước 5: Tắt các thanh đầy để tạo kiểu thanh rỗng

Mã vạch kiểu thanh rỗng chỉ hiển thị viền của các thanh, có thể hữu ích cho các ứng dụng tập trung vào thiết kế.

```python
# Produce an empty‑bars barcode by disabling filled bars
barcode.parameters.barcode.filled_bars = False
```

Khi `filled_bars` là `False`, generator sẽ vẽ các hình rỗng thay vì các hình đặc.

## Bước 6: Lưu hình ảnh mã vạch dưới dạng file PNG

Cuối cùng, ghi mã vạch ra đĩa. PNG là định dạng không mất dữ liệu và được hỗ trợ rộng rãi.

```python
# Save the barcode as a PNG image
barcode.save("output/PlanetEmptyBars.png", BarCodeImageFormat.Png)
```

Phương thức `save` sẽ tự động tạo thư mục đích nếu nó chưa tồn tại.

## Ví dụ đầy đủ – một script hoàn chỉnh, có thể chạy được

Kết hợp tất cả các phần lại với nhau sẽ cho bạn một chương trình độc lập mà bạn có thể chạy ngay lập tức:

```python
# -*- coding: utf-8 -*-
"""
Generate a Planet barcode with empty bars and save it as PNG.
Requires: asposebarcode (pip install asposebarcode)
"""

from asposebarcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# Step 1: Create the generator
barcode = BarcodeGenerator(EncodeTypes.Planet, "123456")

# Step 2: Configure appearance
barcode.parameters.barcode.x_dimension.pixels = 4   # X‑dimension = 4 px
barcode.parameters.barcode.filled_bars = False    # empty‑bars style

# Step 3: Save as PNG
output_path = os.path.join(output_dir, "PlanetEmptyBars.png")
barcode.save(output_path, BarCodeImageFormat.Png)

print(f"Barcode saved to: {output_path}")
```

**Kết quả mong đợi:** Sau khi chạy script, `output/PlanetEmptyBars.png` chứa một hình ảnh 200 × 200 pixel của mã vạch Planet với các thanh rỗng. Mở file trong bất kỳ trình xem ảnh nào sẽ hiển thị mẫu vòng tròn cùng giá trị số được mã hoá bên trong.

## Các biến thể phổ biến và trường hợp đặc biệt

### Chuyển sang ký hiệu khác

Nếu bạn cần QR code, Code 128, hoặc bất kỳ định dạng nào khác, thay `EncodeTypes.Planet` bằng giá trị enum phù hợp:

```python
barcode = BarcodeGenerator(EncodeTypes.QR, "https://example.com")
```

### Thay đổi định dạng ảnh

Aspose.BarCode hỗ trợ PNG, JPEG, BMP và TIFF. Để tạo JPEG thay vì PNG:

```python
barcode.save("output/PlanetEmptyBars.jpg", BarCodeImageFormat.Jpeg)
```

### Điều chỉnh kích thước ảnh mà không mất chất lượng

Bạn có thể kiểm soát kích thước tổng thể của ảnh thông qua thuộc tính `resolution` hoặc bằng cách tỷ lệ đồng thời X‑dimension và Y‑dimension. Đối với in ấn độ phân giải cao, đặt DPI cao hơn:

```python
barcode.parameters.image.resolution = 300  # 300 dpi for print quality
```

### Xử lý chuỗi dữ liệu dài

Ký hiệu Planet có dung lượng dữ liệu giới hạn (tối đa 8 ký tự). Nếu bạn cố gắng mã hoá một chuỗi dài hơn, generator sẽ ném ra ngoại lệ. Hãy kiểm tra độ dài trước khi tạo mã vạch:

```python
data = "123456"
if len(data) > 8:
    raise ValueError("Planet barcode supports a maximum of 8 characters.")
```

## Mẹo và lưu ý

* **Kích hoạt giấy phép:** Đối với môi trường production, áp dụng file giấy phép của bạn ngay trong script bằng `asposebarcode.License().set_license("Aspose.Total.lic")`. Bỏ qua bước này sẽ chèn watermark vào hình ảnh đầu ra.  
* **An toàn đa luồng:** Các instance của `BarcodeGenerator` không an toàn khi dùng đa luồng. Tạo một instance riêng cho mỗi luồng nếu bạn tạo mã vạch song song.  
* **Hiệu năng:** Tái sử dụng một generator cho nhiều giá trị (bằng cách gọi `barcode.value = "new data"`) nhanh hơn so với việc tạo một đối tượng mới mỗi lần.  
* **Đường dẫn file:** Sử dụng `os.path.join` để xây dựng đường dẫn độc lập nền tảng, đặc biệt khi triển khai trên Linux hoặc macOS.  

## Kết luận

Bây giờ bạn đã biết cách tạo hình ảnh mã vạch trong Python với Aspose.BarCode, tùy chỉnh kích thước X, tạo kiểu thanh rỗng và lưu kết quả dưới dạng PNG. Ví dụ đầy đủ có thể được điều chỉnh cho các ký hiệu khác, định dạng đầu ra và kiểu hiển thị, cung cấp cho bạn nền tảng linh hoạt cho bất kỳ tính năng liên quan đến mã vạch nào trong ứng dụng của mình.

**Bước tiếp theo:** Khám phá các từ khóa phụ như *Python barcode generation* bằng cách thử các mã hoá khác nhau, thử nghiệm các cài đặt nén *barcode image PNG*, hoặc tích hợp các hình ảnh đã tạo vào dịch vụ web bằng Flask hoặc FastAPI. Chúc bạn lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã đầy đủ, hoạt động kèm theo giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to create planet barcode PNG with Python](/barcode/english/python-java/general/how-to-create-planet-barcode-png-with-python/)
- [How to create barcode image in Python with Aspose.BarCode](/barcode/english/python-java/general/how-to-create-barcode-image-in-python-with-aspose-barcode/)
- [How to Generate QR Code Image in Python with Aspose.Barcode – Full Guide](/barcode/english/python/general/how-to-generate-qr-code-image-in-python-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}