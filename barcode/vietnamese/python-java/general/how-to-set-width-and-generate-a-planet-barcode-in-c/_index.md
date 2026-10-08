---
category: general
date: 2026-09-16
description: Tìm hiểu cách đặt chiều rộng, cách tạo các thanh trống và cách điền các
  thanh khi bạn tạo mã vạch Planet bằng Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to make empty
- how to fill bars
- generate planet barcode
language: vi
lastmod: 2026-09-16
og_description: Cách đặt chiều rộng, tạo các thanh trống và tô màu các thanh khi bạn
  tạo mã vạch Planet với Aspose.BarCode – hướng dẫn chi tiết từng bước.
og_image_alt: Screenshot showing how to set width for a Planet barcode in C#
og_title: Cách đặt chiều rộng và tạo mã vạch Planet trong C#
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set width, how to make empty bars, and how to fill bars
    when you generate Planet barcode using Aspose.BarCode.
  headline: How to set width and generate a Planet barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách đặt độ rộng và tạo mã vạch Planet trong C#
url: /vi/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đặt độ rộng và tạo mã vạch Planet trong C#

Nếu bạn cần **cách đặt độ rộng** cho mã vạch Planet, hướng dẫn này sẽ trình bày toàn bộ quy trình. Bạn cũng sẽ thấy **cách tạo thanh trống**, **cách tô đầy thanh**, và các bước chính xác để **tạo mã vạch Planet** với Aspose.BarCode cho .NET.

Việc tạo mã vạch Planet dạng bưu chính là phổ biến khi xây dựng các ứng dụng nhãn thư hoặc tích hợp dịch vụ bưu chính. Khi kết thúc tutorial này, bạn sẽ có một chương trình console sẵn sàng chạy, tạo cả hình ảnh thanh đầy và thanh trống, mỗi hình sử dụng cùng một chuỗi dữ liệu.

## Prerequisites

- .NET 6.0 SDK hoặc phiên bản mới hơn (mã cũng hoạt động với .NET Framework 4.7+)
- Visual Studio 2022 hoặc bất kỳ IDE nào hỗ trợ C#
- Gói NuGet Aspose.BarCode for .NET (`Aspose.BarCode`)  
  Cài đặt bằng:

```bash
dotnet add package Aspose.BarCode
```

Không cần cấu hình bổ sung; thư viện tự động xử lý mã hoá hình ảnh bên trong.

## Step 1: Create a console project and add the library

Mở terminal và chạy:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
dotnet add package Aspose.BarCode
```

Lệnh này sẽ tạo một tệp `Program.cs` nơi chúng ta sẽ viết logic tạo mã vạch.

## Step 2: Write the code – how to set width and generate Planet barcode

Mở `Program.cs` và thay thế nội dung bằng ví dụ hoàn chỉnh sau:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Data to encode – the same value is used for both images
        const string data = "123456";

        // -----------------------------------------------------------------
        // Part A: Filled‑bars version (default style)
        // -----------------------------------------------------------------
        // Step 2.1: Create a Planet barcode generator
        var filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 2.2: How to set width – define the width of a single bar in pixels
        // The XDimension controls bar width; 4 pixels yields a clear, printable image
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Save the filled‑bars image (default is FilledBars = true)
        string filledPath = "PostalPlanetFilledBars.png";
        filledGenerator.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to {filledPath}");

        // -----------------------------------------------------------------
        // Part B: Empty‑bars version (unfilled style)
        // -----------------------------------------------------------------
        // Step 3.1: Re‑instantiate the generator for the same data
        var emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, data);

        // Step 3.2: How to set width again – required after re‑instantiation
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3.3: How to make empty – disable the filled‑bars flag
        emptyGenerator.Parameters.Barcode.FilledBars = false;

        // Step 3.4: Save the empty‑bars image
        string emptyPath = "PostalPlanetEmptyBars.png";
        emptyGenerator.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to {emptyPath}");

        // -----------------------------------------------------------------
        // Verification output
        // -----------------------------------------------------------------
        Console.WriteLine("Both barcodes generated successfully.");
    }
}
```

### Why each step matters

- **Cách đặt độ rộng**: Thuộc tính `XDimension.Pixels` ảnh hưởng trực tiếp đến kích thước vật lý của mỗi thanh. Chọn giá trị từ 2 đến 6 pixel sẽ cân bằng giữa khả năng đọc trên màn hình và chất lượng in.
- **Cách tạo thanh trống**: Đặt `FilledBars = false` báo cho trình tạo chỉ vẽ đường viền của các thanh. Kiểu này hữu ích cho việc in “ánh sáng trên nền tối” hoặc khi bạn muốn kết cấu giấy hiện ra phía sau.
- **Cách tô đầy thanh**: Giá trị mặc định `FilledBars = true` tạo các thanh đen đặc, là tiêu chuẩn cho hầu hết máy quét bưu chính.
- **Tạo mã vạch Planet**: Sử dụng `EncodeTypes.Planet` sẽ chọn bộ mã hoá cụ thể mà United States Postal Service (USPS) yêu cầu cho mã vạch Planet.

## Step 3: Build and run the program

Từ thư mục dự án, thực thi:

```bash
dotnet run
```

Bạn sẽ thấy đầu ra console tương tự như:

```
Filled‑bars barcode saved to PostalPlanetFilledBars.png
Empty‑bars barcode saved to PostalPlanetEmptyBars.png
Both barcodes generated successfully.
```

Hai tệp PNG sẽ xuất hiện trong thư mục dự án:

- `PostalPlanetFilledBars.png` – các thanh đen đặc (kiểu mặc định)
- `PostalPlanetEmptyBars.png` – các thanh viền (kiểu trống)

Mở chúng bằng bất kỳ trình xem ảnh nào để xác nhận độ rộng thanh khớp với thiết lập 4 pixel và phiên bản trống hiển thị các thanh chưa được tô.

## Common questions and edge cases

| Question | Answer |
|----------|--------|
| *Tôi có thể dùng định dạng ảnh khác không?* | Có. Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, hoặc `Gif` tùy nhu cầu. |
| *Nếu mã vạch quá rộng so với nhãn của tôi thì sao?* | Giảm `XDimension.Pixels` (ví dụ, xuống `2`) hoặc tăng độ rộng mô-đun của máy in nhãn. |
| *Có cần đặt `Height` thủ công không?* | Thư viện tự động tính chiều cao dựa trên bộ mã hoá. Bạn có thể ghi đè bằng `Parameters.Barcode.BarHeight`. |
| *Kiểu thanh trống có được hỗ trợ trên mọi máy in không?* | Hầu hết các máy in nhiệt hiện đại hỗ trợ cả hai kiểu đầy và trống, nhưng nên kiểm tra bằng bản in thử nếu bạn dùng thiết bị cũ. |
| *Cách thêm chú thích có thể đọc được dưới mã vạch?* | Sử dụng `Parameters.Caption` để bật và định dạng chú thích; đặt `CaptionAbove` thành `false` để đặt nó phía dưới. |

## Pro tips

- **Tái sử dụng cùng một generator** chỉ khi bạn giữ mọi tham số giống hệt nhau. Thay đổi `FilledBars` sau khi lưu không ảnh hưởng tới hình đã lưu, vì vậy việc khởi tạo lại (như trong ví dụ) sẽ đảm bảo khởi đầu sạch sẽ.
- **Tạo hàng loạt**: Đặt mã trong một vòng lặp và thay đổi `data` ở mỗi lần lặp để tạo một loạt mã vạch Planet cho việc gửi thư bulk.
- **Hiệu năng**: Đối với hàng ngàn mã vạch, tạo một thể hiện `BarcodeGenerator` duy nhất, điều chỉnh `XDimension` và `FilledBars` khi cần, và tái sử dụng đối tượng để giảm việc cấp phát bộ nhớ.

## Conclusion

Bây giờ bạn đã biết **cách đặt độ rộng**, **cách tạo thanh trống**, **cách tô đầy thanh**, và các bước chính xác để **tạo mã vạch Planet** với Aspose.BarCode trong C#. Ví dụ hoàn chỉnh, có thể chạy ngay sẽ tạo cả hai tệp PNG thanh đầy và thanh trống, sẵn sàng tích hợp vào bất kỳ quy trình nhãn thư nào.

Tiếp theo, hãy khám phá các chủ đề liên quan như **cách thêm mã QR vào cùng một nhãn**, **tùy chỉnh màu sắc mã vạch**, hoặc **nhúng mã vạch vào tài liệu PDF**. Mỗi chủ đề đều dựa trên những nền tảng đã được trình bày ở đây. Chúc bạn lập trình vui vẻ!

## What Should You Learn Next?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã được minh họa trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ và giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo hình ảnh mã vạch Planet trong C# – Cách tạo mã vạch bưu chính](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Cách tạo mã vạch Code128 với thanh trống trong Java](/barcode/english/java/image-manipulation/generating-barcode-empty-bars/)
- [Cách tạo hình ảnh mã vạch trong Java với Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}