---
category: general
date: 2026-07-30
description: Tạo mã vạch Databar Stacked Omnidirectional bằng Python. Thực hiện theo
  hướng dẫn từng bước này để cấu hình tỷ lệ khung hình, XDimension và xuất PNG bằng
  trình tạo mã vạch Python.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked omnidirectional
- python barcode generator
- databar aspect ratio
- xdimension pixel size
- barcodeimageformat png
language: vi
lastmod: 2026-07-30
og_description: Tạo mã vạch Databar Stacked Omnidirectional trong Python. Hướng dẫn
  này chỉ cách đặt XDimension, điều chỉnh tỷ lệ DataBar và lưu dưới dạng PNG với BarCodeImageFormat.
og_image_alt: Screenshot of a Databar Stacked Omnidirectional barcode saved as a PNG
  file
og_title: Tạo Mã vạch Databar Stacked Omnidirectional – Hướng dẫn Python
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create Databar Stacked Omnidirectional barcode in Python. Follow this
    step‑by‑step guide to configure aspect ratio, XDimension, and export PNG using
    a python barcode generator.
  headline: Create Databar Stacked Omnidirectional Barcode in Python
  type: TechArticle
tags:
- barcode
- python
- databar
title: Tạo mã vạch Databar Stacked Omnidirectional bằng Python
url: /vi/python-java/general/create-databar-stacked-omnidirectional-barcode-in-python/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Databar Stacked Omnidirectional Barcode trong Python

Bạn đã bao giờ cần **tạo databar stacked omnidirectional** barcode trong Python nhưng không chắc bắt đầu từ đâu? Bạn không đơn độc—nhiều nhà phát triển gặp khó khăn này khi lần đầu làm việc với lớp `BarcodeGenerator`. Tin tốt là toàn bộ quá trình khá đơn giản một khi bạn hiểu các thuộc tính chính.

Trong hướng dẫn này, chúng tôi sẽ đi qua một ví dụ đầy đủ, có thể chạy được, sử dụng **python barcode generator** để thiết lập XDimension, điều chỉnh tỷ lệ khía cạnh DataBar, và cuối cùng xuất hai tệp PNG. Khi kết thúc, bạn sẽ nắm vững cách tạo các ký hiệu stacked omnidirectional chất lượng cao cho bất kỳ dự án tồn kho hoặc logistics nào.

## Những gì bạn sẽ học

- Cách khởi tạo một trình tạo **databar stacked omnidirectional** với dữ liệu tải GTIN‑14.  
- Tại sao **kích thước pixel XDimension** quan trọng đối với độ tin cậy khi quét.  
- Ảnh hưởng của **tỷ lệ khía cạnh DataBar** lên độ rộng hàng so với chiều cao.  
- Cách lưu kết quả dưới dạng tệp **BarCodeImageFormat PNG**.  
- Mẹo tái sử dụng cùng một đối tượng generator để tạo nhiều biến thể mà không tốn bộ nhớ thêm.

### Yêu cầu trước

- Python 3.8+ (thư viện chúng tôi dùng là pure‑Python, không cần bánh xe biên dịch).  
- Gói `barcode-generator` (cài đặt bằng `pip install barcode-generator`).  
- Một thư mục bạn có thể ghi – script sẽ ghi hai hình PNG vào đó.

Nếu bạn đã quen với các import cơ bản của Python và mã hướng đối tượng, bạn đã sẵn sàng.

## Tạo Databar Stacked Omnidirectional Barcode – Tổng quan các bước

Dưới đây chúng tôi chia quy trình thành sáu bước ngắn gọn. Mỗi bước là một đoạn mã độc lập mà bạn có thể sao chép‑dán vào REPL hoặc tệp script. Hãy thoải mái thử nghiệm—thay đổi tỷ lệ khía cạnh hoặc XDimension sẽ ngay lập tức cho bạn một phong cách hình ảnh khác.

---

## Bước 1: Tạo Trình tạo Databar Stacked Omnidirectional

Điều đầu tiên chúng ta làm là **tạo databar stacked omnidirectional** generator instance, truyền enum `EncodeTypes` thích hợp và chuỗi dữ liệu.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# Step 1 – initialize the generator with a GTIN‑14 payload
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)
```

> **Tại sao điều này quan trọng:** Cờ `EncodeTypes.DatabarStackedOmniDirectional` thông báo cho thư viện tạo ra một ký hiệu stacked omnirectional, đây là biến thể DataBar duy nhất có thể mã hoá tới 14 chữ số đồng thời vẫn đọc được từ bất kỳ góc nào.

---

## Cấu hình kích thước pixel XDimension

**Kích thước pixel XDimension** kiểm soát mô-đun nhỏ nhất (vạch đen mỏng nhất). Giá trị `2` pixel hoạt động tốt cho hầu hết các trường hợp hiển thị trên màn hình.

```python
# Step 2 – set the smallest module to 2 pixels
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2
```

> **Mẹo chuyên nghiệp:** Nếu bạn dự định in mã vạch ở DPI cao, tăng giá trị này lên 3 hoặc 4 để tránh các cạnh mờ.

---

## Điều chỉnh tỷ lệ khía cạnh DataBar (15)

**Tỷ lệ khía cạnh DataBar** xác định độ rộng của mỗi hàng so với chiều cao của nó. Tỷ lệ `15` tạo ra các hàng rộng hơn, mà nhiều máy quét ưa thích để bắt nhanh chuyển động.

```python
# Step 3 – make rows wider (aspect ratio = 15)
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
```

> **Tại sao 15?** Thông số kỹ thuật chính thức của GS1 đề xuất tỷ lệ từ 10 đến 20 cho các ký hiệu stacked omnidirectional. Chúng tôi chọn `15` làm mặc định cân bằng.

---

## Xuất mã vạch dưới dạng PNG bằng BarCodeImageFormat

Bây giờ trình tạo đã được cấu hình, chúng ta lưu lại hình ảnh. Enum `BarCodeImageFormat.Png` đảm bảo đầu ra không mất dữ liệu, hoàn hảo cho các quy trình xử lý tiếp theo.

```python
# Step 4 – save the first PNG with the 15 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR15.png",
    BarCodeImageFormat.Png
)
```

> **Bạn sẽ thấy:** Mở tệp PNG kết quả; bạn sẽ thấy một mã vạch sạch sẽ, độ tương phản cao với các hàng tương đối rộng.

---

## Thay đổi tỷ lệ khía cạnh DataBar thành 30

Đôi khi bạn cần các hàng cao hơn thay vì rộng hơn—có thể để vừa nhãn hẹp. Thay đổi **tỷ lệ khía cạnh DataBar** thành `30` sẽ làm mỗi hàng cao hơn.

```python
# Step 5 – increase the aspect ratio to make rows taller
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
```

> **Trường hợp biên:** Tỷ lệ rất cao (ví dụ, >40) có thể khiến mã vạch vượt quá chiều cao nhãn tiêu chuẩn, vì vậy hãy thử trên máy in thực tế trước khi quyết định.

---

## Xuất lại mã vạch với tỷ lệ khía cạnh mới

Cuối cùng, chúng ta tái sử dụng cùng một đối tượng `barcode_generator` để ghi một PNG thứ hai. Không cần tạo lại generator—chỉ cần thay đổi thuộc tính và gọi `Save` một lần nữa.

```python
# Step 6 – save the second PNG with the 30 aspect ratio
barcode_generator.Save(
    "YOUR_DIRECTORY/DatabarStackedAR30.png",
    BarCodeImageFormat.Png
)
```

> **Kết quả:** Bây giờ bạn có hai tệp PNG—một với các hàng rộng (`AR15`) và một với các hàng cao (`AR30`). So sánh chúng cạnh nhau để quyết định cái nào phù hợp nhất với cấu hình máy quét của bạn.

---

## Ví dụ hoàn chỉnh hoạt động

Kết hợp tất cả lại, đây là script hoàn chỉnh mà bạn có thể chạy ngay. Thay `YOUR_DIRECTORY` bằng đường dẫn tuyệt đối trên máy của bạn.

```python
from barcode_generator import BarcodeGenerator, EncodeTypes, BarCodeImageFormat

# 1️⃣ Initialize generator
barcode_generator = BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231"
)

# 2️⃣ Set smallest module (XDimension)
barcode_generator.Parameters.Barcode.XDimension.Pixels = 2

# 3️⃣ First aspect ratio – wider rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 15
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR15.png", BarCodeImageFormat.Png)

# 4️⃣ Second aspect ratio – taller rows
barcode_generator.Parameters.Barcode.DataBar.AspectRatio = 30
barcode_generator.Save("YOUR_DIRECTORY/DatabarStackedAR30.png", BarCodeImageFormat.Png)

print("✅ Two PNG files created – AR15 and AR30")
```

**Kết quả mong đợi** (trong console của bạn):

```
✅ Two PNG files created – AR15 and AR30
```

Và hai tệp hình ảnh sẽ xuất hiện trong thư mục đích, sẵn sàng cho các bài kiểm tra quét.

---

## Kết luận

Chúng tôi vừa **tạo databar stacked omnidirectional** barcode trong Python, điều chỉnh **kích thước pixel XDimension**, thử nghiệm với hai cài đặt **tỷ lệ khía cạnh DataBar** khác nhau, và xuất kết quả dưới dạng tệp **BarCodeImageFormat PNG**. Toàn bộ quy trình chỉ cần vài dòng mã, nhưng vẫn cho bạn kiểm soát đầy đủ các đặc điểm hình ảnh quan trọng nhất đối với máy quét.

Tiếp theo? Hãy thử thay payload bằng một GTIN khác, chơi với màu sắc bằng cách chuyển PNG sang ảnh dựa trên bảng màu, hoặc tạo báo cáo PDF nhúng cả hai PNG cạnh nhau. Lớp `BarcodeGenerator` đủ linh hoạt để xử lý tất cả các kịch bản này, vì vậy hãy thoải mái thử nghiệm.

Có câu hỏi về một trường hợp sử dụng cụ thể hoặc gặp lỗi? Để lại bình luận bên dưới, tôi sẽ sẵn sàng giúp đỡ. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với các giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}