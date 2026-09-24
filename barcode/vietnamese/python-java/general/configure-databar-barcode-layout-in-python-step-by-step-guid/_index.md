---
category: general
date: 2026-08-12
description: Cấu hình bố cục mã vạch Databar trong Python nhanh chóng. Học cách đặt
  cột, hàng và lưu hình ảnh với thư viện tạo mã vạch.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- configure databar barcode layout
- Databar Expanded Stacked
- barcode generator Python
- set barcode columns
- set barcode rows
language: vi
lastmod: 2026-08-12
og_description: Cấu hình bố cục mã vạch Databar trong Python để kiểm soát cột, hàng
  và đầu ra hình ảnh. Tham khảo hướng dẫn này để có giải pháp sẵn sàng chạy.
og_image_alt: Screenshot of a Databar Expanded Stacked barcode with custom column
  layout
og_title: Cấu hình bố cục mã vạch Databar trong Python – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  headline: Configure Databar barcode layout in Python – step‑by‑step guide
  type: TechArticle
- description: Configure Databar barcode layout in Python quickly. Learn to set columns,
    rows, and save images with the barcode generator library.
  name: Configure Databar barcode layout in Python – step‑by‑step guide
  steps:
  - name: Import the required classes
    text: '```python from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
      ```'
  - name: Create a barcode generator for Databar Expanded Stacked
    text: '```python # Initialize the generator with the desired symbology and value
      barcode_generator = BarcodeGenerator( EncodeTypes.DatabarExpandedStacked, "Databar
      Expanded Stacked long" ) ```'
  - name: Set the number of columns (horizontal layout)
    text: '```python # Configure the layout to use 4 columns barcode_generator.parameters.barcode.data_bar.columns
      = 4 ```'
  - name: Save the barcode image with the column layout
    text: '```python # Save the image as a PNG file barcode_generator.save("output/ExpandedCols4.png",
      BarCodeImageFormat.Png) ```'
  - name: Create a second generator for the same barcode type (row layout)
    text: If you prefer a vertical stack, you work with rows instead of columns. The
      code below re‑uses the same value but creates a fresh `BarcodeGenerator` instance
      to avoid mixing column and row settings.
  - name: Set the number of rows (vertical layout)
    text: '```python # Configure the layout to use 3 rows barcode_generator.parameters.barcode.data_bar.rows
      = 3 ```'
  - name: Save the barcode image with the row layout
    text: '```python # Save the vertically stacked barcode barcode_generator.save("output/ExpandedRows3.png",
      BarCodeImageFormat.Png) ```'
  type: HowTo
tags:
- barcode
- Python
- Databar
- image generation
title: Cấu hình bố cục mã vạch Databar trong Python – hướng dẫn từng bước
url: /vi/python-java/general/configure-databar-barcode-layout-in-python-step-by-step-guid/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cấu hình bố cục mã vạch Databar trong Python – hướng dẫn từng bước

Nếu bạn cần **cấu hình bố cục mã vạch Databar trong Python**, hướng dẫn này sẽ dẫn bạn qua toàn bộ quá trình. Bạn sẽ thấy cách đặt số cột hoặc hàng cho mã vạch Databar Expanded Stacked và cách lưu hình ảnh kết quả chỉ với một lần gọi tới thư viện tạo mã vạch.

Kiểm soát bố cục là điều cần thiết khi bạn nhúng mã vạch lên bao bì hẹp, biên lai hoặc màn hình di động. Trong các phần dưới đây, chúng tôi sẽ đề cập đến các import cần thiết, hai tùy chọn bố cục (cột và hàng), và các thực tiễn tốt nhất để lưu ảnh PNG sạch sẽ.

## Những gì bạn cần

* Python 3.8 hoặc mới hơn
* `aspose.barcode` (hoặc bất kỳ gói tạo mã vạch tương thích nào) đã được cài đặt  
  ```bash
  pip install aspose-barcode
  ```
* Quyền ghi vào thư mục nơi các tệp PNG sẽ được lưu

Không cần công cụ bên ngoài nào thêm—thư viện tự xử lý việc render, scaling và mã hoá hình ảnh bên trong.

## Cách cấu hình bố cục mã vạch Databar trong Python

Cốt lõi của giải pháp là lớp `BarcodeGenerator`. Nó nhận một enum `EncodeTypes` xác định loại mã vạch—trong trường hợp này là `EncodeTypes.DatabarExpandedStacked`. Sau khi tạo generator, bạn có thể điều chỉnh bố cục bằng cách đặt các thuộc tính `columns` hoặc `rows` trên đối tượng tham số `data_bar`.

### Bước 1: Nhập các lớp cần thiết

```python
from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
```

Các import này cho phép bạn truy cập vào generator, enum cho các loại Databar, và hằng số định dạng ảnh PNG.

### Bước 2: Tạo một barcode generator cho Databar Expanded Stacked

```python
# Initialize the generator with the desired symbology and value
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

*Tại sao bước này?*  
`EncodeTypes.DatabarExpandedStacked` yêu cầu thư viện tạo ra ký hiệu **Databar Expanded Stacked**, hỗ trợ các chuỗi số dài hơn trong khi vẫn giữ kích thước gọn nhẹ. Tham số thứ hai là dữ liệu cần mã hoá; nó có thể là bất kỳ chuỗi nào đáp ứng tiêu chuẩn Databar.

### Bước 3: Đặt số cột (bố cục ngang)

```python
# Configure the layout to use 4 columns
barcode_generator.parameters.barcode.data_bar.columns = 4
```

**set barcode columns** là cụm từ chính cho thao tác này. Khi bạn tăng số cột, mã vạch sẽ lan rộng theo chiều ngang, điều này có thể hữu ích cho nhãn rộng. Thư viện tự động tính lại độ rộng module để giữ kích thước tổng thể nhất quán.

#### Mẹo chuyên nghiệp
Số cột tối đa cho Databar Expanded Stacked là 8. Đặt giá trị lớn hơn giới hạn sẽ bị giới hạn lại ở mức tối đa, nhưng tốt hơn là bạn nên kiểm tra đầu vào trước.

### Bước 4: Lưu ảnh mã vạch với bố cục cột

```python
# Save the image as a PNG file
barcode_generator.save("output/ExpandedCols4.png", BarCodeImageFormat.Png)
```

**save barcode image** là hành động ghi mã vạch đã render ra đĩa. PNG là định dạng không mất dữ liệu, giữ được các cạnh sắc nét cần thiết cho việc quét đáng tin cậy.

### Bước 5: Tạo một generator thứ hai cho cùng loại mã vạch (bố cục hàng)

Nếu bạn muốn một chồng dọc, bạn sẽ làm việc với hàng thay vì cột. Đoạn mã dưới đây tái sử dụng cùng một giá trị nhưng tạo một thể hiện `BarcodeGenerator` mới để tránh trộn lẫn cài đặt cột và hàng.

```python
# New generator instance for row configuration
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
```

### Bước 6: Đặt số hàng (bố cục dọc)

```python
# Configure the layout to use 3 rows
barcode_generator.parameters.barcode.data_bar.rows = 3
```

**set barcode rows** sắp xếp các module mã vạch theo chiều dọc. Bố cục ba hàng giảm chiều cao của mỗi chồng riêng lẻ, làm cho mã vạch phù hợp với biên lai hẹp hoặc màn hình di động.

#### Trường hợp đặc biệt
Nếu bạn đặt `rows` thành 1, thư viện sẽ tạo một Databar một hàng (tương đương với Databar tiêu chuẩn). Các giá trị dưới 1 sẽ bị bỏ qua và đặt lại về mặc định (1 hàng).

### Bước 7: Lưu ảnh mã vạch với bố cục hàng

```python
# Save the vertically stacked barcode
barcode_generator.save("output/ExpandedRows3.png", BarCodeImageFormat.Png)
```

Một lần nữa, chúng ta **save barcode image** bằng PNG để giữ độ nét của đầu ra.

## Ví dụ đầy đủ có thể chạy

Kết hợp tất cả các phần lại với nhau sẽ cho bạn một script tự chứa mà bạn có thể đưa vào bất kỳ dự án Python nào.

```python
# ------------------------------------------------------------
# configure_databar_layout.py
# Demonstrates how to configure Databar barcode layout in Python
# ------------------------------------------------------------

from aspose.barcode import BarcodeGenerator, EncodeTypes, BarCodeImageFormat
import os

# Ensure the output directory exists
output_dir = "output"
os.makedirs(output_dir, exist_ok=True)

# -----------------------------------------------------------------
# 1️⃣ Column layout – 4 columns
# -----------------------------------------------------------------
col_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
col_generator.parameters.barcode.data_bar.columns = 4   # set barcode columns
col_path = os.path.join(output_dir, "ExpandedCols4.png")
col_generator.save(col_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Column layout saved to {col_path}")

# -----------------------------------------------------------------
# 2️⃣ Row layout – 3 rows
# -----------------------------------------------------------------
row_generator = BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long"
)
row_generator.parameters.barcode.data_bar.rows = 3      # set barcode rows
row_path = os.path.join(output_dir, "ExpandedRows3.png")
row_generator.save(row_path, BarCodeImageFormat.Png)   # save barcode image
print(f"Row layout saved to {row_path}")
```

**Kết quả mong đợi**

Chạy script sẽ tạo ra hai tệp PNG:

* `output/ExpandedCols4.png` – một mã vạch kéo dài qua bốn cột
* `output/ExpandedRows3.png` – một mã vạch nén thành ba hàng

Cả hai hình ảnh đều có thể mở bằng bất kỳ trình xem ảnh nào hoặc nhập trực tiếp vào hoá đơn PDF, mẫu nhãn, hoặc trang web.

## Câu hỏi thường gặp và khắc phục sự cố

| Câu hỏi | Trả lời |
|----------|--------|
| *Nếu mã vạch bị mờ thì sao?* | Tăng độ phân giải ảnh bằng cách đặt `barcode_generator.parameters.image_width` và `image_height` trước khi gọi `save`. |
| *Tôi có thể dùng các định dạng ảnh khác không?* | Có. Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, hoặc `Gif` tùy nhu cầu. |
| *Có giới hạn độ dài dữ liệu không?* | Databar Expanded Stacked hỗ trợ tối đa 74 ký tự số. Vượt quá giới hạn sẽ gây ra `ArgumentException`. |
| *Làm sao để thay đổi màu nền trước?* | Sử dụng `barcode_generator.parameters.barcode.color = Color.Blue` (import `System.Drawing.Color`). |
| *Tôi có thể kết hợp cả cột và hàng không?* | Không. API coi cột và hàng là các chế độ bố cục loại trừ lẫn nhau. Chỉ chọn một trong mỗi instance của mã vạch. |

## Các bước tiếp theo

Bây giờ bạn đã có thể **cấu hình bố cục mã vạch Databar**, hãy xem xét khám phá các chủ đề liên quan sau:

* **Thêm chú thích văn bản** – sử dụng `barcode_generator.parameters.barcode.code_text` để hiển thị giá trị đã mã hoá dưới hình ảnh.
* **Nhúng mã vạch vào PDF** – kết hợp PNG đã tạo với `aspose.pdf` để tạo tài liệu có thể in.
* **Kích thước động** – tính toán số cột hoặc hàng tối ưu dựa trên kích thước nhãn tại thời gian chạy.
* **Xử lý hàng loạt** – lặp qua một CSV các mã sản phẩm để tự động tạo thư viện ảnh mã vạch.

Thử nghiệm với các giá trị cột và hàng khác nhau để xem chúng ảnh hưởng như thế nào đến độ tin cậy khi quét trên thiết bị mục tiêu của bạn. Bạn càng thử nghiệm, bạn sẽ càng hiểu rõ các đánh đổi giữa kích thước mã vạch, khả năng đọc và hạn chế không gian.

---

*Chúc lập trình vui vẻ! Nếu bạn thấy hướng dẫn này hữu ích, hãy chia sẻ với đồng nghiệp hoặc để lại bình luận về những thách thức bố cục mà bạn gặp phải.*

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao phủ các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo ảnh mã vạch DotCode – hàng & cột (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Tạo ảnh mã vạch c# – Cấu hình Codablock F Hàng & Cột](/barcode/english/net/codablock-f-encoding/codablock-f-row-column-configuration/)
- [Điều chỉnh chiều cao mã vạch Databar một chiều](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}