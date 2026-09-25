---
category: general
date: 2026-08-22
description: Tìm hiểu cách tạo mã vạch micro PDF417 bằng C# và tạo hình ảnh PNG cho
  mã vạch. Bao gồm việc thiết lập kích thước mã vạch và lưu tệp.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: vi
lastmod: 2026-08-22
og_description: Tạo mã vạch micro PDF417 bằng C# và xuất ra dạng PNG. Tham khảo hướng
  dẫn này để thiết lập kích thước mã vạch và nhanh chóng tạo hình ảnh mã vạch.
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: Tạo mã vạch micro PDF417 bằng C# – hướng dẫn lập trình đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: Cách tạo mã vạch micro PDF417 trong C# – hướng dẫn từng bước
url: /vi/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch micro PDF417 trong C# – hướng dẫn từng bước

Nếu bạn cần **tạo mã vạch micro PDF417** cho hệ thống bán vé, nhãn hàng tồn kho hoặc quét trên thiết bị di động, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Bạn sẽ thấy chương trình C# đầy đủ tạo ra ảnh PNG của mã vạch, học cách đặt kích thước mã vạch và hiểu mỗi tùy chọn cấu hình.

Khi kết thúc hướng dẫn này, bạn sẽ có thể tạo ra hình ảnh mã vạch độ phân giải cao, tùy chỉnh X‑dimension, chọn số cột và lưu kết quả dưới dạng tệp PNG—tất cả chỉ với vài dòng mã.

## Những gì bạn cần

- .NET 6.0 SDK hoặc phiên bản mới hơn (mã này hoạt động với .NET Core và .NET Framework)
- Visual Studio 2022 hoặc bất kỳ IDE nào hỗ trợ C#
- Gói NuGet **Aspose.BarCode for .NET** (hoặc bất kỳ thư viện nào hỗ trợ `EncodeTypes.MicroPdf417`)
- Kiến thức cơ bản về cú pháp C#

> **Mẹo:** Phiên bản cộng đồng miễn phí của Aspose.BarCode đủ cho việc phát triển và thử nghiệm. Đối với môi trường sản xuất, hãy mua giấy phép để loại bỏ watermark đánh giá.

## Bước 1: Cài đặt thư viện mã vạch

Mở terminal trong thư mục dự án của bạn và chạy:

```bash
dotnet add package Aspose.BarCode
```

Lệnh này sẽ thêm assembly `Aspose.BarCode`, cung cấp lớp `BarcodeGenerator` được sử dụng để **tạo ảnh mã vạch C#** trong các ứng dụng.

## Bước 2: Khởi tạo trình tạo – tạo mã vạch micro PDF417

Dòng lệnh đầu tiên tạo một thể hiện `BarcodeGenerator` được cấu hình cho ký hiệu Micro PDF417 và cung cấp dữ liệu bạn muốn mã hoá.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*Tại sao điều này quan trọng*: Enum `EncodeTypes.MicroPdf417` chỉ cho thư viện sử dụng phiên bản gọn của PDF417, phù hợp cho các nhãn nhỏ và màn hình di động.

## Bước 3: Cách đặt kích thước mã vạch trong C#

Tinh chỉnh độ rộng mô-đun (X‑dimension) kiểm soát mật độ hiển thị của mã vạch. Giá trị nhỏ hơn tạo ra hình ảnh sắc nét hơn, trong khi giá trị lớn hơn giúp mã vạch dễ quét hơn từ khoảng cách xa.

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tại sao bạn nên đặt kích thước**: Nếu không điều chỉnh X‑dimension, giá trị mặc định có thể tạo ra mã vạch mờ khi hiển thị ở DPI cao. Đặt nó thành 2 pixel là sự cân bằng tốt cho hầu hết các lần quét trên màn hình.

## Bước 4: Chọn số cột – kiểm soát chiều rộng mã vạch

Micro PDF417 cho phép từ 1 đến 4 cột. Nhiều cột hơn sẽ nén dữ liệu theo chiều ngang, giảm chiều rộng tổng thể của ảnh.

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*Trường hợp đặc biệt*: Nếu bạn yêu cầu 5 cột, thư viện sẽ ném ra ngoại lệ `ArgumentOutOfRangeException`. Luôn giữ trong phạm vi được tài liệu chỉ định.

## Bước 5: Cách tạo PNG cho mã vạch – lưu ảnh

Bây giờ bạn có thể xuất mã vạch đã tạo ra thành tệp PNG. PNG giữ nguyên chất lượng không mất dữ liệu, điều này rất quan trọng cho việc quét đáng tin cậy.

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Khi bạn chạy chương trình, sẽ thấy thông báo trên console xác nhận vị trí tệp. Tệp `MicroPdf417.png` tạo ra sẽ trông như sau:

![Ảnh chụp màn hình hiển thị mã vạch micro PDF417 được tạo bằng C#](micro-pdf417-example.png "Mã vạch micro PDF417 đã tạo")

*Văn bản thay thế hình ảnh*: **mã vạch micro PDF417 được tạo bằng C#** – minh họa kết quả cuối cùng sau khi áp dụng các thiết lập kích thước và số cột.

## Bước 6: Chạy và xác minh đầu ra

1. Xây dựng dự án: `dotnet build`.
2. Thực thi: `dotnet run`.
3. Mở `MicroPdf417.png` trên máy tính để bàn và quét bằng ứng dụng quét mã vạch trên điện thoại di động.

Bạn sẽ thấy văn bản **“Sample text”** được giải mã. Nếu trình quét báo lỗi, hãy kiểm tra lại X‑dimension và số cột – các giá trị cực đoan có thể làm cho mã vạch quá dày đối với một số thiết bị.

## Các biến thể thường gặp và khắc phục sự cố

| Tình huống | Điều chỉnh |
|-----------|------------|
| **Cần mã vạch lớn hơn cho máy in độ phân giải thấp** | Tăng `XDimension.Pixels` lên 3 hoặc 4. |
| **Muốn mã vạch cao hơn mà không thay đổi chiều rộng** | Đặt `generator.Parameters.Barcode.Pdf417.Rows` (phạm vi hàng 3‑90). |
| **Tạo nhiều mã vạch trong vòng lặp** | Tái sử dụng cùng một thể hiện `BarcodeGenerator` và chỉ thay đổi `CodeText` trước mỗi lần `Save`. |
| **Lưu dưới dạng JPEG thay vì PNG** | Thay thế `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg`. |
| **Chạy trên .NET Framework 4.7** | Mã giống nhau vẫn hoạt động; chỉ cần tham chiếu tới `Aspose.BarCode.dll` phù hợp. |

## Danh sách mã nguồn đầy đủ (có thể chạy)

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**Kết quả mong đợi** – một tệp PNG kích thước 200 × 100 pixel chứa mã vạch Micro PDF417 sắc nét, giải mã thành “Sample text”.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch micro PDF417** trong C#, **đặt kích thước mã vạch**, và **tạo ảnh PNG cho mã vạch**. Ví dụ đầy đủ minh họa mọi bước cần thiết—từ cài đặt thư viện đến lưu tệp cuối cùng—để bạn có thể nhúng việc tạo mã vạch trực tiếp vào ứng dụng của mình.

Tiếp theo, hãy khám phá các chủ đề liên quan như **tạo mã QR với Aspose.BarCode**, **tùy chỉnh màu sắc**, hoặc **nhúng mã vạch vào tài liệu PDF**. Mỗi chủ đề đều dựa trên các nguyên tắc cơ bản của `BarcodeGenerator` đã được trình bày ở đây.

Bạn có thể thoải mái thử nghiệm với các chuỗi dữ liệu khác nhau, số cột và giá trị X‑dimension để phù hợp với môi trường quét của mình. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có ví dụ mã đầy đủ hoạt động kèm theo giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch – PDF417 Compact với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách tạo mã vạch PDF417 – Mã hoá PDF417 Compact](/barcode/english/net/compact-pdf417-encoding/)
- [Cách tạo mã vạch Aztec với Aspose.BarCode cho .NET](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}