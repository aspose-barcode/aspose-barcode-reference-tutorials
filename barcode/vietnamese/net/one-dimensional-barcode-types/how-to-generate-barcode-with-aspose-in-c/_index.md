---
category: general
date: 2026-09-19
description: Cách tạo mã vạch bằng Aspose trong C# – hướng dẫn từng bước để tạo mã
  vạch với Aspose nhanh chóng và đáng tin cậy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: vi
lastmod: 2026-09-19
og_description: Cách tạo mã vạch với Aspose trong C#. Tham khảo hướng dẫn này để tạo
  mã vạch bằng Aspose, cấu hình MacroPdf417 và lưu dưới dạng PNG.
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: Cách tạo mã vạch với Aspose – hướng dẫn đầy đủ C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: Cách tạo mã vạch với Aspose trong C#
url: /vi/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch với Aspose trong C#

Việc tạo mã vạch trong C# rất đơn giản khi bạn sử dụng thư viện Aspose.BarCode. Hướng dẫn này sẽ chỉ cho bạn cách **tạo mã vạch với Aspose** từng bước, bao gồm định dạng MacroPdf417, các cài đặt hiển thị chung, và cách lưu kết quả dưới dạng ảnh PNG.

Bạn sẽ học được cách:

* Cài đặt và tham chiếu Aspose.BarCode cho .NET  
* Cấu hình các thuộc tính đặc thù của MacroPdf417 như file ID, segment ID và checksum  
* Điều chỉnh các tùy chọn hiển thị như X‑dimension và số cột  
* Xuất mã vạch ra file ảnh  

Bạn không cần kinh nghiệm trước với Aspose—chỉ cần hiểu cơ bản về C# và Visual Studio.

## Prerequisites

Trước khi bắt đầu, hãy chắc chắn bạn có:

| Yêu cầu | Chi tiết |
|-------------|--------|
| .NET runtime | .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+) |
| IDE | Visual Studio 2022, Rider, hoặc bất kỳ trình soạn thảo nào hỗ trợ C# |
| Aspose.BarCode | Gói NuGet `Aspose.BarCode` (bản dùng thử miễn phí hoặc phiên bản có giấy phép) |
| Basic C# knowledge | Quen thuộc với các câu lệnh `using` và khởi tạo đối tượng |

Bạn có thể thêm Aspose.BarCode vào dự án của mình qua NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## How to generate barcode in C# – overall workflow

Quá trình bao gồm bốn bước logic:

1. **Tạo một thể hiện `BarcodeGenerator`** với loại mã hoá mong muốn (MacroPdf417) và văn bản bạn muốn mã hoá.  
2. **Đặt các tùy chọn hiển thị chung** như X‑dimension và số cột.  
3. **Cấu hình các thuộc tính đặc thù của MacroPdf417** như file ID, segment ID và timestamp.  
4. **Lưu mã vạch** sang định dạng file bạn chọn (PNG trong ví dụ này).  

Mỗi bước sẽ được giải thích chi tiết bên dưới.

## Step 1: Create a barcode generator for MacroPdf417

Lớp `BarcodeGenerator` là điểm vào cho mọi tác vụ tạo mã vạch. Khi bạn khởi tạo nó, bạn truyền hai đối số:

* `EncodeTypes.MacroPdf417` – cho Aspose biết sử dụng ký hiệu MacroPdf417.  
* Chuỗi dữ liệu – văn bản sẽ được mã hoá trong mã vạch.  

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **Tại sao điều này quan trọng:** MacroPdf417 là một mã vạch hai chiều có thể chứa lượng dữ liệu lớn và hỗ trợ các tính năng macro như phân đoạn file, rất hữu ích cho việc truyền các file lớn thành các phần.

## Step 2: Set common barcode appearance options

Mặc dù MacroPdf417 có nhiều cài đặt chuyên biệt, bạn vẫn muốn kiểm soát mật độ và bố cục hiển thị. Các tham số phổ biến nhất là:

* **X‑dimension** – chiều rộng của mô-đun nhỏ nhất (pixel). Giá trị nhỏ hơn tạo ra hình ảnh dày đặc hơn.  
* **Columns** – số cột dữ liệu trên mỗi hàng; số lớn hơn giảm chiều cao của mã vạch.  

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **Mẹo:** Giữ `XDimension` trong khoảng 2 đến 4 pixel cho hầu hết các trường hợp hiển thị trên màn hình. Giá trị lớn hơn cải thiện khả năng đọc trên máy in độ phân giải thấp nhưng làm tăng kích thước tổng thể của ảnh.

## Step 3: Configure MacroPdf417‑specific properties

MacroPdf417 thêm một tập hợp các trường siêu dữ liệu cho phép bạn chia một file lớn thành nhiều segment mã vạch. Các thuộc tính sau thường được yêu cầu:

| Thuộc tính | Mục đích |
|----------|---------|
| `MacroPdf417FileID` | Mã định danh duy nhất cho toàn bộ file (tối đa 8 chữ số). |
| `MacroPdf417SegmentID` | Chỉ mục của segment hiện tại (bắt đầu từ 0). |
| `MacroPdf417SegmentsCount` | Tổng số segment trong file. |
| `MacroPdf417FileName` | Tên file gốc có thể đọc được bởi con người. |
| `MacroPdf417Checksum` | Checksum CCITT‑16 tùy chọn để phát hiện lỗi. |
| `MacroPdf417FileSize` | Kích thước của file gốc tính bằng byte. |
| `MacroPdf417TimeStamp` | Dấu thời gian khi file được tạo. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Chuỗi tùy chọn để xác định người gửi/nhận. |
| `MacroPdf417Terminator` | Xác định mã vạch có phải là segment cuối cùng (`Set`) hay một segment ở giữa (`Unset`). |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **Tại sao các trường này hữu ích:**  
> *Khi bạn cần truyền một tài liệu lớn qua kênh băng thông thấp, bạn có thể chia tài liệu thành nhiều mã vạch MacroPdf417. Người nhận sẽ tái tạo lại file gốc bằng cách đọc siêu dữ liệu của mỗi segment.*

## Step 4: Save the generated barcode as an image

Aspose hỗ trợ nhiều định dạng đầu ra: PNG, JPEG, BMP, TIFF, SVG và PDF. PNG là định dạng không mất dữ liệu, lý tưởng cho web hoặc hiển thị UI.

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Khi bạn chạy chương trình, bạn sẽ tìm thấy một file PNG trông tương tự như hình minh họa dưới đây.

![MacroPdf417 barcode generated with Aspose in C#](placeholder-image.png){.img-fluid alt="cách tạo mã vạch với Aspose trong C#"}

> **Kết quả mong đợi:** Một ảnh PNG kích thước 300 × 150 pixel hiển thị mã vạch MacroPdf417 mã hoá văn bản “Sample” cùng với siêu dữ liệu macro bạn đã cung cấp.

## Full, runnable example

Kết hợp mọi thứ lại, đây là chương trình hoàn chỉnh mà bạn có thể sao chép, dán và chạy:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

Chạy chương trình với `dotnet run` (hoặc nhấn **F5** trong Visual Studio). Sau khi thực thi, kiểm tra xem file PNG đã tồn tại và mở mà không có lỗi.

## Common questions and edge‑case handling

### What if I need a different image format?
Aspose hỗ trợ `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg` và `Pdf`. Chỉ cần thay `BarCodeImageFormat.Png` bằng giá trị enum mong muốn.

### How do I generate multiple segments automatically?
Bạn có thể đặt đoạn mã trên trong một vòng lặp, tăng `MacroPdf417SegmentID` ở mỗi lần lặp và cập nhật chuỗi dữ liệu. Hãy nhớ giữ `MacroPdf417SegmentsCount` cố định cho tất cả các segment.

### What if the data exceeds the capacity of a single MacroPdf417 symbol?
MacroPdf417 được thiết kế cho tải trọng lớn, nhưng mỗi mã vạch vẫn có giới hạn lý thuyết (≈ 1.1 KB mỗi segment). Chia file nguồn thành các phần vừa với giới hạn này, sau đó mã hoá mỗi phần thành một segment riêng.

### Does the checksum need to be calculated manually?
Aspose có thể tự động tạo checksum CCITT‑16 nếu bạn đặt `MacroPdf417Checksum` thành `0`. Trong ví dụ chúng tôi đã cung cấp một giá trị cố định để minh họa; trong mã thực tế bạn thường để thư viện tự tính.

### How can I change the barcode’s foreground/background colors?
Sử dụng các thuộc tính `BarColor` và `BackColor`:

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## Conclusion

Bạn đã biết **cách tạo mã vạch** trong C# bằng Aspose.BarCode và, cụ thể, **cách tạo mã vạch với Aspose** cho ký hiệu MacroPdf417. Hướng dẫn đã bao phủ việc cài đặt, cấu hình hiển thị và các trường đặc thù của macro.

## What Should You Learn Next?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch DataMatrix bằng Aspose.BarCode cho .NET – Hướng dẫn chi tiết](/barcode/english/net/datamatrix-barcode-configuration/)
- [Cách tạo ảnh mã vạch PDF417 trong C# với Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cách tạo mã vạch Aztec với tỷ lệ khung tùy chỉnh bằng Aspose.BarCode cho .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}