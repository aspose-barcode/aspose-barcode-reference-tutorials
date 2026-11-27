---
category: general
date: 2026-11-27
description: Tìm hiểu cách điều chỉnh chiều cao thanh mã vạch trong trình tạo mã vạch
  DataBar Omni‑Directional. Mã từng bước cho thấy việc đặt chiều cao thành 30 px và
  60 px.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- adjust barcode bar height
- DataBar Omni‑Directional barcode
- set XDimension
- barcode image format
- BarCodeImageFormat
- barcode generator python
language: vi
lastmod: 2026-11-27
og_description: Điều chỉnh chiều cao thanh mã vạch trong trình tạo mã vạch DataBar
  Omni‑Directional bằng Python. Thực hiện hướng dẫn đầy đủ để thiết lập chiều cao,
  kích thước X và lưu ảnh PNG.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode with adjusted bar height
og_title: Điều chỉnh chiều cao thanh mã vạch trong trình tạo DataBar Omni‑Directional
schemas:
- author: GroupDocs
  dateModified: '2026-11-27'
  description: Learn how to adjust barcode bar height in a DataBar Omni‑Directional
    barcode generator. Step‑by‑step code shows setting heights to 30 px and 60 px.
  headline: How to adjust barcode bar height in DataBar Omni‑Directional generator
  type: TechArticle
tags:
- barcode
- python
- DataBar
- imaging
title: Cách điều chỉnh chiều cao thanh mã vạch trong trình tạo DataBar Omni‑Directional
url: /vi/python-java/general/how-to-adjust-barcode-bar-height-in-databar-omni-directional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách điều chỉnh chiều cao thanh mã vạch trong trình tạo DataBar Omni‑Directional

Nếu bạn cần **điều chỉnh chiều cao thanh mã vạch** cho mã DataBar Omni‑Directional, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Bạn sẽ thấy một ví dụ Python đầy đủ, có thể chạy được, thay đổi chiều cao thanh từ 30 px lên 60 px trong khi giữ nguyên kích thước X‑dimension và định dạng ảnh.

Thay đổi kích thước hiển thị của mã vạch là yêu cầu phổ biến khi mã vạch phải vừa với kích thước nhãn hoặc quy tắc thiết kế cụ thể. Ngoài chiều cao thanh, bạn cũng có thể muốn tinh chỉnh **X‑dimension** (kích thước mô-đun) hoặc chọn **định dạng ảnh mã vạch** khác như PNG hoặc JPEG.

Trong tutorial này bạn sẽ:

* Cài đặt thư viện cần thiết (GroupDocs.Barcode for Python)
* Tạo trình tạo mã DataBar Omni‑Directional
* Đặt kích thước mô-đun bằng `XDimension`
* Điều chỉnh thuộc tính chiều cao thanh hai lần
* Lưu các ảnh kết quả ở **BarCodeImageFormat** mong muốn

Không cần kinh nghiệm trước với GroupDocs API—chỉ cần kiến thức cơ bản về Python.

## Yêu cầu trước

Trước khi bắt đầu, hãy đảm bảo bạn có:

* Python 3.8 hoặc mới hơn đã được cài đặt
* Gói `groupdocs.barcode` (`pip install groupdocs-barcode`)  
* Quyền ghi vào thư mục nơi các file PNG sẽ được lưu

Nếu bạn chưa quen với **mã DataBar Omni‑Directional**, nó mã hoá một GTIN 14‑chữ số và được sử dụng rộng rãi trong bán lẻ để quét từ bất kỳ hướng nào.

## Bước 1: Thiết lập trình tạo mã DataBar Omni‑Directional

Đầu tiên, nhập các lớp cần thiết và khởi tạo trình tạo với dữ liệu GTIN bạn muốn mã hoá.

```python
from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Create a generator for a DataBar Omni‑Directional barcode
# The string "(01)12345678901231" follows the GS1 Application Identifier syntax
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")
```

*Lý do quan trọng:* Hằng số `EncodeTypes.DatabarOmniDirectional` cho thư viện biết tạo symbology Omni‑Directional. Chuỗi dữ liệu bao gồm AI `(01)` đánh dấu giá trị GTIN‑14.

## Bước 2: Định nghĩa X‑dimension (kích thước mô-đun)

X‑dimension kiểm soát độ rộng của thanh hẹp nhất. Giá trị thường dùng cho hiển thị trên màn hình là **2 px mỗi mô-đun**.

```python
# Set the module (X‑dimension) size – 2 px per module
gen.parameters.barcode.x_dimension.pixels = 2
```

Việc **set XDimension** nhất quán giúp mã vạch được thu phóng đúng trên các máy in và máy quét khác nhau.

## Bước 3: Điều chỉnh chiều cao thanh thành 30 px và lưu ảnh

Bây giờ chúng ta thay đổi thuộc tính chiều cao thanh. Chiều cao đầu tiên sẽ là **30 px**, phù hợp cho các nhãn nhỏ.

```python
# Define the first bar height (30 px)
gen.parameters.barcode.bar_height.pixels = 30

# Save the barcode as a PNG image
gen.save("output/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png)
```

Hằng số `BarCodeImageFormat.Png` chọn **định dạng ảnh mã vạch** PNG, giữ nguyên chất lượng không mất dữ liệu.

### Kết quả mong đợi

File `DatabarBarHeight30Pixels.png` chứa một mã DataBar Omni‑Directional có các thanh cao 30 px. Dưới đây là bản xem trước mẫu:

![Mã DataBar với chiều cao thanh 30 px](images/databar_30px.png "Mã DataBar với chiều cao thanh 30 px")

> **Mẹo:** Nếu bạn mở PNG trong trình chỉnh sửa ảnh, sẽ thấy chiều cao thanh chính xác. Các thanh hẹp có độ rộng 2 px, như đã định nghĩa ở trên.

## Bước 4: Thay đổi chiều cao thanh lên 60 px cho mã vạch cao hơn

Đối với các ứng dụng cần diện tích hiển thị lớn hơn—ví dụ nhãn vận chuyển—bạn có thể tăng chiều cao thanh lên **60 px**.

```python
# Change the bar height to 60 px for a taller barcode
gen.parameters.barcode.bar_height.pixels = 60
```

Chỉ thuộc tính `BarHeight` được thay đổi; X‑dimension và quá trình mã hoá vẫn giữ nguyên, vì vậy mã vạch vẫn có thể quét được.

## Bước 5: Lưu ảnh mã vạch đã cập nhật

Cuối cùng, ghi mã vạch cao hơn vào một file PNG thứ hai.

```python
# Save the updated barcode image
gen.save("output/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png)
```

### Kết quả mong đợi

File `DatabarBarHeight60Pixels.png` hiển thị cùng dữ liệu đã mã hoá, nhưng mỗi thanh bây giờ cao 60 px. Sự khác biệt trực quan được minh họa dưới đây:

![Mã DataBar với chiều cao thanh 60 px](images/databar_60px.png "Mã DataBar với chiều cao thanh 60 px")

## Ví dụ đầy đủ, có thể chạy

Kết hợp tất cả lại, đây là script hoàn chỉnh bạn có thể sao chép‑dán vào file tên `adjust_barcode_height.py` và chạy ngay.

```python
# adjust_barcode_height.py
# Demonstrates how to adjust barcode bar height for a DataBar Omni‑Directional barcode

from groupdocs.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# 1️⃣ Create the generator with GTIN data
gen = BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231")

# 2️⃣ Set module size (X‑dimension) to 2 px
gen.parameters.barcode.x_dimension.pixels = 2

# 3️⃣ First bar height: 30 px
gen.parameters.barcode.bar_height.pixels = 30
gen.save(os.path.join(output_dir, "DatabarBarHeight30Pixels.png"), BarCodeImageFormat.Png)

# 4️⃣ Second bar height: 60 px
gen.parameters.barcode.bar_height.pixels = 60
gen.save(os.path.join(output_dir, "DatabarBarHeight60Pixels.png"), BarCodeImageFormat.Png)

print(f"Barcodes saved to '{output_dir}'")
```

Chạy script:

```bash
python adjust_barcode_height.py
```

Bạn sẽ thấy hai file PNG trong thư mục `output`, mỗi file phản ánh chiều cao thanh bạn đã đặt.

## Câu hỏi thường gặp và các trường hợp đặc biệt

| Câu hỏi | Trả lời |
|----------|--------|
| **Tôi có thể dùng JPEG thay vì PNG không?** | Có. Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg`. JPEG là dạng nén mất dữ liệu, vì vậy nên ưu tiên PNG để quét chính xác. |
| **Nếu tôi cần chiều cao thanh không phải bội số của 10 thì sao?** | Thuộc tính `BarHeight.Pixels` chấp nhận bất kỳ giá trị nguyên nào. Chỉ cần gán số pixel mong muốn (ví dụ `45`). |
| **Thay đổi chiều cao thanh có ảnh hưởng tới dữ liệu đã mã hoá không?** | Không. Chỉ thay đổi cách hiển thị; chuỗi dữ liệu gốc vẫn không thay đổi. |
| **Làm sao thay đổi X‑dimension sau khi đã lưu ảnh đầu tiên?** | Bạn có thể sửa `gen.parameters.barcode.x_dimension.pixels` bất kỳ lúc nào trước khi gọi `save()`. Thay đổi sẽ áp dụng cho các ảnh tiếp theo. |
| **Trình tạo có an toàn khi dùng đa luồng không?** | Đối tượng `BarcodeGenerator` không được đảm bảo an toàn khi dùng đa luồng. Hãy tạo một thể hiện riêng cho mỗi luồng nếu bạn tạo mã vạch đồng thời. |

## Kết luận

Bạn đã biết cách **điều chỉnh chiều cao thanh mã vạch** trong trình tạo DataBar Omni‑Directional bằng Python. Tutorial đã hướng dẫn cách tạo trình tạo, thiết lập **X‑dimension**, sửa thuộc tính **chiều cao thanh mã vạch**, và lưu ảnh ở **định dạng ảnh mã vạch** mong muốn.

Từ đây, bạn có thể thử nghiệm với các chiều cao khác, kích thước mô-đun khác, hoặc chuyển sang các định dạng ảnh thay thế như JPEG hoặc BMP. Bạn cũng có thể khám phá các tính năng **barcode generator python** khác như thêm văn bản có thể đọc được hoặc thay đổi màu sắc.

Chúc lập trình vui vẻ, và giữ cho mã vạch của bạn luôn sắc nét và kích thước hoàn hảo!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên đều bao gồm mã mẫu đầy đủ với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Create omni directional databar and barcode image in Python](/barcode/english/python-java/general/create-omni-directional-databar-and-barcode-image-in-python/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}