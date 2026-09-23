---
category: general
date: 2026-08-12
description: Tạo databar omnidirectional bằng Python và học cách tạo hình ảnh mã vạch
  bằng Python sử dụng Aspose.BarCode. Thực hiện theo hướng dẫn từng bước để có giải
  pháp hoàn chỉnh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omni directional databar
- create barcode image python
language: vi
lastmod: 2026-08-12
og_description: Tạo databar đa hướng bằng Python và tạo hình ảnh mã vạch trong vài
  phút. Hướng dẫn này trình bày một ví dụ đầy đủ, có thể chạy được.
og_image_alt: example of create omni directional databar barcode image in Python
og_title: Tạo thanh dữ liệu đa hướng – hướng dẫn Python đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create omni directional databar with Python and learn how to create
    barcode image python using Aspose.BarCode. Follow the step‑by‑step guide for a
    complete solution.
  headline: Create omni directional databar and barcode image in Python
  type: TechArticle
tags:
- barcode
- Python
- Aspose
- DataBar
title: Tạo hình ảnh databar và mã vạch đa hướng bằng Python
url: /vi/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo omni directional databar và hình ảnh mã vạch trong Python

Nếu bạn cần **tạo omni directional databar** trong một dự án Python, hướng dẫn này sẽ chỉ cho bạn cách thực hiện và cũng cách **tạo hình ảnh mã vạch python** bằng thư viện Aspose.BarCode. Bạn sẽ nhận được một script sẵn sàng chạy tạo ra hai tệp PNG với tỷ lệ khung hình khác nhau.

Việc tạo DataBar tuân theo chuẩn Omni‑directional là yêu cầu phổ biến cho các ứng dụng bán lẻ và logistics. Bài học bao gồm cài đặt, cấu hình kích thước X, điều chỉnh tỷ lệ khung hình và lưu các hình ảnh cuối cùng. Không cần dịch vụ bên ngoài; mọi thứ chạy cục bộ.

## Những gì bạn sẽ cần

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* Python 3.8 trở lên đã được cài đặt trên máy của bạn.
* Truy cập tới terminal hoặc command prompt.
* Quyền ghi vào thư mục sẽ lưu các hình ảnh mã vạch.

Phụ thuộc bên thứ ba duy nhất là **Aspose.BarCode for Python via .NET**, hỗ trợ loại DataBar Omni‑directional ngay từ đầu.

## Bước 1: Cài đặt Aspose.BarCode cho Python

Aspose.BarCode cung cấp lớp `BarcodeGenerator` được sử dụng trong mã mẫu. Cài đặt gói bằng `pip`:

```bash
pip install aspose-barcode
```

Gói này bao gồm các binding runtime .NET cần thiết, vì vậy bạn không cần cài đặt .NET SDK riêng.

## Bước 2: Nhập thư viện và tạo generator

Dòng đầu tiên của script tạo một generator cho Omni‑directional DataBar dạng stacked. Giá trị GTIN‑14 `(01)12345678901231` được dùng làm dữ liệu mẫu.

```python
# Step 2: Import classes and create the generator
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a stacked Omni‑directional DataBar with the required data
barcode_generator = BarcodeGenerator(
    EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
    "(01)12345678901231"
)
```

*Lý do bước này quan trọng*: Hằng số `EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL` cho thư viện biết mã hoá giá trị dưới dạng Omni‑directional DataBar, định dạng mà nhiều máy quét điểm bán hàng yêu cầu.

## Bước 3: Đặt kích thước X (độ rộng mô-đun)

Kích thước X xác định độ rộng của mô-đun thanh nhỏ nhất. Giá trị `2` pixel tạo ra mã vạch rõ ràng, dễ đọc mà không làm tệp quá lớn.

```python
# Step 3: Set the basic X‑dimension (width of the smallest module) in pixels
barcode_generator.parameters.barcode.x_dimension.pixels = 2
```

*Lý do bước này quan trọng*: Điều chỉnh kích thước X giúp cân bằng giữa khả năng đọc và kích thước hình ảnh. Kích thước X quá nhỏ có thể hiển thị kém trên máy in độ phân giải thấp.

## Bước 4: Cấu hình tỷ lệ khung hình và lưu hình ảnh đầu tiên

Tỷ lệ khung hình ảnh hưởng đến chiều cao tổng thể của DataBar so với chiều rộng. Tỷ lệ `15` tạo phong cách trực quan gọn gàng.

```python
# Step 4: Configure an aspect ratio of 15 and save the first image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 15
barcode_generator.save("output/StackedAR15.png", BarCodeImageFormat.Png)
```

> **Mẹo chuyên nghiệp**: Sử dụng `pathlib.Path` để xây dựng đường dẫn đầu ra, nó sẽ tự động tạo các thư mục còn thiếu.

```python
from pathlib import Path

output_dir = Path("output")
output_dir.mkdir(parents=True, exist_ok=True)
barcode_generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)
```

## Bước 5: Thay đổi tỷ lệ khung hình cho phong cách trực quan thứ hai và lưu hình ảnh khác

Chuyển tỷ lệ khung hình thành `30` tạo ra mã vạch cao hơn, có thể cần cho một số phần cứng máy quét cụ thể.

```python
# Step 5: Change the aspect ratio to 30 and save the second image
barcode_generator.parameters.barcode.data_bar.aspect_ratio = 30
barcode_generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)
```

*Lý do bước này quan trọng*: Các nhà bán lẻ và thiết bị quét có các ràng buộc kích thước khác nhau. Cung cấp cả hai tỷ lệ trong một script cho phép bạn tạo phong cách cần thiết mà không phải sao chép mã.

## Script đầy đủ – tạo omni directional databar và barcode image python

Dưới đây là ví dụ hoàn chỉnh, có thể chạy được, bao gồm tất cả các bước trước. Lưu lại dưới tên `generate_databar.py` và chạy bằng `python generate_databar.py`.

```python
#!/usr/bin/env python3
"""
Complete example that creates an omni directional databar
and demonstrates how to create barcode image python using Aspose.BarCode.
"""

# Import required classes
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
from pathlib import Path

def main():
    # Define output directory and ensure it exists
    output_dir = Path("output")
    output_dir.mkdir(parents=True, exist_ok=True)

    # Initialize the generator with Omni‑directional DataBar data
    generator = BarcodeGenerator(
        EncodeTypes.DATABAR_STACKED_OMNIDIRECTIONAL,
        "(01)12345678901231"
    )

    # Set X‑dimension to 2 pixels for good readability
    generator.parameters.barcode.x_dimension.pixels = 2

    # First visual style – aspect ratio 15
    generator.parameters.barcode.data_bar.aspect_ratio = 15
    generator.save(output_dir / "StackedAR15.png", BarCodeImageFormat.Png)

    # Second visual style – aspect ratio 30
    generator.parameters.barcode.data_bar.aspect_ratio = 30
    generator.save(output_dir / "StackedAR30.png", BarCodeImageFormat.Png)

    print(f"Images saved to: {output_dir.resolve()}")

if __name__ == "__main__":
    main()
```

### Kết quả mong đợi

Chạy script sẽ tạo ra các tệp sau:

```
output/StackedAR15.png   # DataBar with aspect ratio 15
output/StackedAR30.png   # DataBar with aspect ratio 30
```

Cả hai hình ảnh đều hiển thị một Omni‑directional DataBar hợp lệ, có thể quét được bằng thiết bị bán lẻ tiêu chuẩn.

![ví dụ tạo omni directional databar barcode image trong Python](example_databar.png "tạo omni directional databar barcode image python")

*Hình ảnh trên chỉ là placeholder minh họa hai tệp PNG đã lưu.*

## Xử lý các vấn đề thường gặp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| `ImportError: No module named aspose` | Aspose.BarCode chưa được cài đặt hoặc được cài trong môi trường khác. | Kích hoạt môi trường ảo đúng và chạy `pip install aspose-barcode`. |
| `PermissionError` khi lưu | Script không có quyền ghi vào thư mục đích. | Chọn thư mục bạn sở hữu hoặc chạy script với quyền thích hợp. |
| Mã vạch không quét được | Kích thước X quá thấp hoặc tỷ lệ khung hình không phù hợp với máy quét. | Tăng `x_dimension.pixels` lên 3 hoặc 4, và thử các giá trị `aspect_ratio` khác (ví dụ: 20, 25). |
| Thiếu runtime .NET | Aspose.BarCode phụ thuộc vào runtime .NET trên Windows/Linux. | Cài đặt runtime .NET mới nhất từ trang Microsoft; tài liệu gói cung cấp hướng dẫn cho từng nền tảng. |

## Mở rộng ví dụ

Bạn có thể điều chỉnh script để tạo các biến thể DataBar khác (ví dụ: `DATABAR_STACKED`, `DATABAR_EXPANDED`). Thay đổi hằng số `EncodeTypes` cho phù hợp:

```python
generator = BarcodeGenerator(EncodeTypes.DATABAR_EXPANDED, "(01)12345678901231")
```

Nếu cần nhúng mã vạch vào PDF, Aspose.PDF for Python có thể nhập trực tiếp tệp PNG hoặc bạn có thể dùng phương thức `save` với `BarCodeImageFormat.Pdf`.

## Kết luận

Bài hướng dẫn này đã chỉ cách **tạo omni directional databar** và cách **tạo barcode image python** bằng Aspose.BarCode. Giờ đây bạn đã có một script hoàn chỉnh, có thể tái tạo, tạo ra hai tệp PNG với tỷ lệ khung hình khác nhau, xử lý các vấn đề thường gặp và có thể mở rộng sang các định dạng mã vạch khác.

Tiếp theo, hãy khám phá việc tạo QR code, thêm mã vạch vào hóa đơn PDF, hoặc tự động xử lý hàng loạt cho danh mục sản phẩm lớn. Mỗi chủ đề này đều dựa trên mẫu `BarcodeGenerator` đã được trình bày ở đây. Chúc bạn lập trình vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong bài này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [How to create barcode image and render it in Java](/barcode/english/java/barcode-rendering-techniques/rendering-barcode-image-instance/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}