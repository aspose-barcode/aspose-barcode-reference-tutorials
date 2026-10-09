---
category: general
date: 2026-10-08
description: Tìm hiểu cách thay đổi kích thước hình ảnh mã vạch với ví dụ trình tạo
  mã vạch C#, điều chỉnh chiều cao thanh từ 30 px lên 60 px chỉ trong vài dòng mã.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: vi
lastmod: 2026-10-08
og_description: Cách thay đổi kích thước mã vạch nhanh chóng bằng ví dụ trình tạo
  mã vạch C#. Điều chỉnh chiều cao thanh, lưu file PNG và tránh các lỗi thường gặp.
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: Cách thay đổi kích thước mã vạch trong C# – ví dụ tạo mã từng bước
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: Cách thay đổi kích thước mã vạch bằng ví dụ trình tạo mã vạch trong C#
url: /vi/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thay đổi kích thước mã vạch bằng ví dụ tạo mã vạch trong C#

Nếu bạn cần **cách thay đổi kích thước mã vạch** trong một dự án .NET, hướng dẫn này sẽ trình bày giải pháp đầy đủ. Bạn sẽ thấy một **ví dụ tạo mã vạch C#** ngắn gọn, thay đổi chiều cao thanh từ 30 px lên 60 px và lưu mỗi phiên bản dưới dạng tệp PNG.

Thay đổi kích thước mã vạch thường cần thiết khi cùng một dữ liệu phải xuất hiện trên biên lai, nhãn mác hoặc trang sản phẩm với các tỷ lệ hiển thị khác nhau. Thay vì chỉnh sửa ảnh raster bằng một trình chỉnh sửa bên ngoài, bạn có thể điều chỉnh kích thước mã vạch bằng chương trình, giữ nguyên tính toàn vẹn của dữ liệu.

Trong hướng dẫn này bạn sẽ:

* Thiết lập bộ tạo mã vạch DataBar Omni‑Directional.
* Sửa đổi các tham số X‑dimension và bar height.
* Lưu hai ảnh với chiều cao khác nhau.
* Hiểu tại sao việc thay đổi bar height hoạt động và những trường hợp đặc biệt cần lưu ý.

> **Tiền đề** – Bạn đã có môi trường phát triển .NET (Visual Studio 2022 hoặc mới hơn) và thư viện mã vạch cung cấp `BarcodeGenerator`, `EncodeTypes` và `BarCodeImageFormat`. Mã này hoạt động với phiên bản mới nhất của thư viện tính đến tháng 10 2026.

## Các yêu cầu trước cho ví dụ tạo mã vạch C#

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

| Mục | Lý do |
|------|--------|
| .NET 6.0 SDK hoặc mới hơn | Cung cấp runtime và các tính năng ngôn ngữ được sử dụng trong mẫu. |
| Thư viện mã vạch (ví dụ: Aspose.BarCode, Dynamsoft, hoặc bất kỳ thư viện nào cung cấp `BarcodeGenerator`) | Cung cấp enum `EncodeTypes.DatabarOmniDirectional` và các phương thức xuất ảnh. |
| Thư mục có thể ghi được (ví dụ: `C:\Temp\Barcodes\`) | Mẫu sẽ lưu các tệp PNG vào vị trí này. |
| Kiến thức cơ bản về C# | Hướng dẫn giả định bạn đã quen với lớp, thuộc tính và chuỗi nội suy. |

Cài đặt thư viện qua NuGet nếu bạn chưa làm:

```bash
dotnet add package Aspose.BarCode
```

Thay thế tên gói bằng gói bạn thực sự sử dụng; giao diện API được hiển thị bên dưới là chung cho hầu hết các SDK mã vạch.

## Cách thay đổi kích thước mã vạch – bước 1: tạo bộ tạo

Bước đầu tiên là khởi tạo một `BarcodeGenerator` với ký hiệu và dữ liệu mong muốn. Trong ví dụ này chúng ta tạo mã **DataBar Omni‑Directional** mã hoá giá trị GTIN‑14.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Tại sao điều này quan trọng:** Enum `EncodeTypes.DatabarOmniDirectional` cho thư viện biết chuẩn mã vạch nào sẽ được dùng. Chuỗi dữ liệu tuân theo Application Identifier `(01)` của GS1 cho GTIN 14 chữ số, đảm bảo mã vạch tuân thủ các tiêu chuẩn thương mại toàn cầu.

## Cách thay đổi kích thước mã vạch – bước 2: định nghĩa độ rộng mô-đun và chiều cao thanh ban đầu

Kích thước trực quan của mã vạch phụ thuộc vào hai tham số:

* **X‑dimension** – độ rộng của thanh nhỏ nhất (mô-đun). Được đo bằng pixel hoặc milimet.
* **Bar height** – chiều dài dọc của các thanh.

Đặt các giá trị này trước khi lưu sẽ đảm bảo ảnh được tạo ra khớp với kích thước bạn cần.

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Giải thích:** X‑dimension 2 px tạo ra một mã vạch gọn gàng nhưng vẫn quét được đáng tin cậy. Chiều cao 30 px là mặc định phổ biến cho các nhãn nhỏ. Bạn có thể điều chỉnh X‑dimension độc lập với chiều cao nếu muốn mẫu dày đặc hơn hoặc rời rạc hơn.

## Cách thay đổi kích thước mã vạch – bước 3: lưu ảnh đầu tiên (chiều cao 30 px)

Bây giờ xuất mã vạch ra tệp PNG. Phương thức `Save` nhận đường dẫn tệp và enum định dạng ảnh.

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Kết quả:** `DatabarBarHeight30Pixels.png` chứa một mã vạch cao 30 px. Bạn có thể mở tệp trong bất kỳ trình xem ảnh nào để kiểm tra kích thước.

## Cách thay đổi kích thước mã vạch – bước 4: thay đổi chiều cao thanh lên 60 px

Để tạo phiên bản lớn hơn, chỉ cần sửa thuộc tính `BarHeight`. Bộ tạo sẽ tiếp tục sử dụng cùng dữ liệu và X‑dimension, vì vậy mẫu mã vạch vẫn giống nhau—chỉ thay đổi kích thước hiển thị.

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Tại sao cách này hoạt động:** Engine render mã vạch tính toán hình học của mỗi thanh khi cần. Cập nhật thuộc tính chiều cao trước lần gọi `Save` tiếp theo sẽ kích hoạt việc raster hoá lại với kích thước mới.

## Cách thay đổi kích thước mã vạch – bước 5: lưu ảnh thứ hai (chiều cao 60 px)

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Bây giờ bạn có hai tệp PNG, một nhỏ (30 px) và một lớn hơn (60 px), sẵn sàng sử dụng cho các kích thước nhãn khác nhau.

## Mã nguồn đầy đủ cho ví dụ tạo mã vạch C#

Dưới đây là chương trình hoàn chỉnh, có thể chạy ngay. Sao chép vào một dự án console mới để thử.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Đầu ra mong đợi trong console:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

Sau khi chạy, mở hai tệp PNG để thấy sự khác biệt về hình ảnh. Cả hai mã vạch đều mã hoá cùng giá trị GTIN‑14 và sẽ quét được giống nhau, bất kể chiều cao.

## Tại sao điều chỉnh chiều cao thanh an toàn cho việc quét

Máy quét mã vạch đọc mẫu các mô-đun sáng và tối, không phải số pixel tuyệt đối. Miễn là **X‑dimension** vẫn nằm trong dung sai của máy quét (thường từ 0.5 mm đến 2 mm ở đơn vị vật lý), việc thay đổi chiều cao không ảnh hưởng đến khả năng đọc. Thư viện tự động mở rộng các mô-đun, duy trì các vùng yên tĩnh và mẫu căn chỉnh cần thiết.

## Những lỗi thường gặp và cách tránh chúng

| Vấn đề | Cách khắc phục |
|---------|------------|
| **Thư mục đầu ra không tồn tại** | Gọi `Directory.CreateDirectory(outputPath)` trước khi lưu. |
| **X‑dimension không đúng gây mờ khi quét** | Giữ `XDimension.Pixels` trong khoảng 1 px đến 4 px cho hầu hết máy in; kiểm tra bằng máy quét thực tế. |
| **Sử dụng định dạng raster cho mã vạch rất lớn** | Chuyển sang `BarCodeImageFormat.Svg` để có khả năng mở rộng vô hạn mà không bị pixel hoá. |
| **Quên đặt lại `BarHeight` trước lần lưu thứ hai** | Đảm bảo bạn gán chiều cao mới **trước** khi gọi lại `Save`. |

## Mẹo chuyên nghiệp: tạo nhiều kích thước trong một vòng lặp

Nếu bạn cần một loạt các chiều cao (ví dụ: 30 px, 45 px, 60 px), một vòng `foreach` đơn giản sẽ giảm thiểu việc lặp lại mã:

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

Mô hình này mở rộng tốt cho việc xử lý hàng loạt danh mục sản phẩm.

## Các trường hợp đặc biệt: định dạng ảnh và cài đặt DPI khác nhau

* **Xuất SVG** – Dùng `BarCodeImageFormat.Svg` để tạo tệp vector có thể thay đổi kích thước mà không mất chất lượng.
* **PNG DPI cao** – Đặt `generator.Parameters.Image.DpiX` và `DpiY` thành 300 hoặc 600 cho ảnh sẵn sàng in; chiều cao thanh vẫn được đo bằng pixel, vì vậy tăng tương ứng.
* **Ký hiệu không chuẩn** – Một số loại mã vạch (ví dụ: QR Code) có thuộc tính `Size` riêng thay vì `BarHeight`. Tham khảo tài liệu thư viện cho những trường hợp này.

## Kiểm tra mã vạch đã thay đổi kích thước

1. Mở mỗi PNG trong trình xem ảnh và xác nhận kích thước pixel (ví dụ: 150 × 30 px so với 150 × 60 px).  
2. In ảnh ở tỷ lệ 100 %.  
3. Quét bằng máy quét mã vạch cầm tay hoặc ứng dụng di động. Dữ liệu giải mã phải giống nhau.

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Ví dụ tạo mã vạch trong C# – đặt chiều rộng và chiều cao](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [Cách thay đổi kích thước mã vạch trong C# với Aspose.BarCode – hướng dẫn chi tiết](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [Cách lưu ảnh mã vạch với Barcode Generator C# – hướng dẫn chi tiết](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}