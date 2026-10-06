---
category: general
date: 2026-09-16
description: Tìm hiểu cách tạo mã vạch và thiết lập kích thước mã vạch trong C#. Hướng
  dẫn từng bước sử dụng Aspose.BarCode để tạo hình ảnh Micro PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- set barcode size
language: vi
lastmod: 2026-09-16
og_description: Cách tạo mã vạch trong C# và thiết lập kích thước mã vạch với Aspose.BarCode.
  Theo dõi hướng dẫn ngắn gọn này để tạo ra file PNG Micro PDF417.
og_image_alt: Example output showing how to generate barcode using C#
og_title: Cách tạo mã vạch trong C# – hướng dẫn đầy đủ Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to generate barcode and set barcode size in C#. Step‑by‑step
    guide using Aspose.BarCode to create a Micro PDF417 image.
  headline: How to generate barcode in C# with Aspose.BarCode
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Cách tạo mã vạch trong C# với Aspose.BarCode
url: /vi/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch trong C# với Aspose.BarCode

Nếu bạn cần biết **cách tạo mã vạch** trong một dự án .NET, hướng dẫn này sẽ đưa bạn qua toàn bộ quá trình sử dụng thư viện Aspose.BarCode. Bạn cũng sẽ học cách **đặt kích thước mã vạch** để hình ảnh phù hợp với giao diện người dùng hoặc yêu cầu in ấn của bạn.

Hướng dẫn bao gồm mọi thứ từ cài đặt gói NuGet đến cấu hình ký hiệu Micro PDF417 và lưu nó dưới dạng tệp PNG. Khi kết thúc, bạn sẽ có một mẫu mã có thể chạy được mà bạn có thể chèn vào bất kỳ ứng dụng console hoặc web C# nào.

## Những gì bạn cần

- .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.6+)
- Visual Studio 2022 hoặc bất kỳ IDE nào hỗ trợ C#
- Kết nối Internet để tải xuống gói NuGet **Aspose.BarCode**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Kiến thức cơ bản về cú pháp C#

## Cách tạo mã vạch với Aspose.BarCode

Bước đầu tiên là tạo một thể hiện `BarcodeGenerator` biết sẽ sử dụng ký hiệu nào và dữ liệu nào để mã hoá.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Micro PDF417 barcode generator with the data to encode
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");
```

**Tại sao điều này quan trọng:** `EncodeTypes.MicroPdf417` chỉ cho thư viện tạo ra một biến thể PDF417 gọn nhẹ, lý tưởng cho các nhãn nhỏ hoặc dấu vết giống QR‑code. Chuỗi `"Micro data"` trở thành dữ liệu có thể đọc được bởi con người được nhúng trong mã vạch.

## Đặt kích thước và kích thước mô-đun của mã vạch

Một mã vạch có thể đọc được phải có kích thước mô-đun (X) phù hợp và đủ cột để chứa dữ liệu. Đây là nơi bạn **đặt kích thước mã vạch**.

```csharp
// Step 2: Define the module size (X dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Set the maximum number of columns for the Micro PDF417 symbol
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

- **XDimension** kiểm soát độ rộng của thanh nhỏ nhất (“module”). Giá trị `2` pixel hoạt động tốt cho hiển thị trên màn hình; tăng giá trị này cho việc in độ phân giải cao.
- **Pdf417.Columns** giới hạn số cột dọc. Định dạng Micro PDF417 chỉ hỗ trợ tối đa 7 cột; `4` cung cấp kích thước cân bằng mà không làm giảm khả năng chứa dữ liệu.

> **Mẹo chuyên nghiệp:** Nếu hình ảnh tạo ra quá nhỏ, tăng `XDimension.Pixels` lên `3` hoặc `4`. Ngược lại, nếu không gian UI chật, bạn có thể giảm xuống `1`, nhưng hãy chắc chắn rằng máy quét bạn dự định sử dụng vẫn có thể đọc được ký hiệu.

## Lưu hình ảnh mã vạch

Sau khi cấu hình kích thước, bạn chỉ cần hướng dẫn trình tạo ghi hình ảnh ra đĩa.

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("micro.png", BarCodeImageFormat.Png);
```

Phương thức `Save` chấp nhận bất kỳ định dạng nào được Aspose.BarCode hỗ trợ (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`). PNG là không mất dữ liệu, giữ được các cạnh sắc nét cần thiết cho việc quét đáng tin cậy.

**Kết quả mong đợi:** Một tệp có tên `micro.png` sẽ xuất hiện trong thư mục làm việc của dự án. Mở nó sẽ hiển thị một mã vạch Micro PDF417 nhỏ, độ tương phản cao, sẵn sàng để thử nghiệm với bất kỳ máy quét tiêu chuẩn nào.

## Ví dụ hoàn chỉnh

Kết hợp tất cả các phần lại với nhau sẽ cho bạn một chương trình tự chứa mà bạn có thể chạy ngay lập tức.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Micro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");

            // Set size parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // column count

            // Choose output path (adjust as needed)
            string outputPath = "micro.png";

            // Save as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Chạy chương trình (`dotnet run` từ console) và bạn sẽ thấy thông báo xác nhận. PNG được tạo ra có thể nhúng vào báo cáo, in trên nhãn sản phẩm, hoặc hiển thị trên trang web.

## Các câu hỏi thường gặp và trường hợp đặc biệt

| Câu hỏi | Trả lời |
|---|---|
| **Tôi có thể tạo các loại mã vạch khác không?** | Có. Thay `EncodeTypes.MicroPdf417` bằng bất kỳ giá trị nào từ enum `EncodeTypes` (ví dụ: `EncodeTypes.Code128`, `EncodeTypes.QR`). |
| **Nếu tôi cần hình ảnh lớn hơn thì sao?** | Tăng `XDimension.Pixels` hoặc sử dụng `generator.Parameters.Image.Width/Height` để ép kích thước pixel cụ thể. |
| **Thư viện có hỗ trợ nền trong suốt không?** | Đặt `generator.Parameters.Barcode.BackColor = System.Drawing.Color.Transparent;` trước khi gọi `Save`. |
| **Làm sao để đọc lại mã vạch?** | Sử dụng `Aspose.BarCode.BarCodeReader` trên hình ảnh đã lưu; nó sẽ tự động phát hiện ký hiệu. |
| **PNG có an toàn cho việc in ấn không?** | PNG là không mất dữ liệu, nhưng đối với in CMYK nên cân nhắc lưu dưới dạng TIFF (`BarCodeImageFormat.Tiff`). |

## Kết luận

Bây giờ bạn đã biết **cách tạo mã vạch** trong C# và cách **đặt kích thước mã vạch** bằng Aspose.BarCode. Ví dụ hoàn chỉnh minh họa việc tạo ký hiệu Micro PDF417, điều chỉnh kích thước của nó và xuất ra tệp PNG. Với nền tảng này, bạn có thể khám phá các ký hiệu khác, tùy chỉnh màu sắc, hoặc tích hợp việc tạo mã vạch vào các dịch vụ ASP.NET Core.

### Các bước tiếp theo

- Thử tạo một mã QR (`EncodeTypes.QR`) và so sánh kích thước mô-đun.  
- Thử nghiệm với `generator.Parameters.Image` để thêm lề hoặc thay đổi DPI cho đầu ra sẵn sàng in.  
- Kết hợp việc tạo mã vạch với **Aspose.PDF** để nhúng hình ảnh trực tiếp vào báo cáo PDF.

Chúc lập trình vui vẻ, và tận hưởng sự linh hoạt mà Aspose.BarCode mang lại cho các dự án mã vạch .NET của bạn!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoạt động đầy đủ với các giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo hình ảnh mã vạch PDF417 trong C# với Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cách tạo mã vạch PDF417 với Aspose – Hướng dẫn đầy đủ](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Cách tạo mã vạch trong C# – Hướng dẫn đầy đủ Aspose.BarCode](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}