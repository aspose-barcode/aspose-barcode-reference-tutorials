---
category: general
date: 2026-10-21
description: Tạo mã vạch pdf417 nhanh chóng trong C#. Tìm hiểu cách tạo mã vạch pdf417
  với bố cục tùy chỉnh, cột, hàng và xuất ra PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: vi
lastmod: 2026-10-21
og_description: Tạo mã vạch pdf417 trong C#. Theo hướng dẫn này để học cách tạo mã
  vạch pdf417 với các cột, hàng tùy chỉnh và xuất ra PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Tạo mã vạch pdf417 trong C# – hướng dẫn chi tiết từng bước
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: Tạo mã vạch pdf417 trong C# với các cột và hàng tùy chỉnh
url: /vi/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch pdf417 trong C# – hướng dẫn lập trình đầy đủ

Nếu bạn cần **tạo mã vạch pdf417** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chỉ với vài dòng code. Bạn sẽ thấy một ví dụ thực tế cấu hình số cột và hàng, sau đó lưu kết quả dưới dạng ảnh PNG. Cách tiếp cận này hoạt động với bất kỳ văn bản nào bạn muốn mã hoá, vì vậy bạn có thể áp dụng cho hoá đơn, vé, hoặc thẻ ID.

Việc **tạo mã vạch pdf417** thường cảm giác như một nhiệm vụ riêng biệt so với phần còn lại của codebase. Khi kết thúc tutorial này, bạn sẽ hiểu vì sao các tham số bố cục quan trọng, cách kiểm soát chất lượng ảnh, và những lời gọi thư viện nào cần thiết để **tạo mã vạch pdf417** một cách đáng tin cậy.

## Những gì bạn cần

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Một IDE hỗ trợ C# (Visual Studio, VS Code, Rider, v.v.)  
* Gói NuGet **Aspose.BarCode for .NET** (hoặc bất kỳ thư viện mã vạch tương thích nào)  

Bạn có thể thêm thư viện bằng lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

Thư viện cung cấp lớp `BarcodeGenerator` được sử dụng xuyên suốt tutorial này.

## Bước 1: Tạo một thể hiện của barcode generator

Dòng đầu tiên tạo một đối tượng biết cách **tạo mã vạch pdf417**. Bạn phải chỉ định loại mã hoá (`EncodeTypes.Pdf417`) và văn bản bạn muốn mã hoá.

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*Lý do bước này quan trọng* – `BarcodeGenerator` bao gói tất cả các cài đặt cho mã vạch. Khởi tạo nó với `EncodeTypes` đúng sẽ báo cho engine sử dụng symbology PDF417 thay vì QR, Code128, hoặc các định dạng khác.

## Bước 2: Cấu hình bố cục PDF417

PDF417 cho phép bạn kiểm soát số cột và hàng, điều này ảnh hưởng trực tiếp đến kích thước và mật độ của mã vạch. Điều chỉnh các giá trị này là cốt lõi của **cách tạo mã vạch pdf417** với bố cục tùy chỉnh.

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*Lý do bạn có thể muốn thay đổi các giá trị này* – Nhiều cột sẽ làm giảm chiều cao của mã vạch, trong khi nhiều hàng sẽ tăng chiều rộng. Chọn các giá trị phù hợp với thiết bị quét mục tiêu và khu vực in có sẵn.

> **Mẹo chuyên nghiệp:** Nếu bạn bỏ qua việc chỉ định hàng, thư viện sẽ tự động tính toán số lượng tối ưu dựa trên độ dài dữ liệu. Việc đặt hàng một cách rõ ràng hữu ích khi bạn cần một kích thước ảnh cố định cho bố cục UI.

## Bước 3: Chọn định dạng ảnh và lưu file

Sau khi cấu hình bố cục, bạn có thể render mã vạch thành ảnh. Ví dụ dưới đây lưu mã vạch dưới dạng file PNG, nhưng bạn cũng có thể chọn JPEG, BMP, hoặc TIFF.

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Khi code chạy, `CustomLayout.png` sẽ chứa một **mã vạch pdf417** rõ ràng, phù hợp với các cài đặt cột/hàng mà bạn đã cung cấp.

### Kết quả mong đợi

Mở `CustomLayout.png` sẽ hiển thị một mã vạch hình chữ nhật với bốn cột dữ liệu và chín hàng. Quét ảnh này bằng bất kỳ trình đọc PDF417 nào sẽ trả về văn bản gốc **“Sample Text”**.

![Generated PDF417 barcode example](generated-pdf417.png){: .center-image alt="Mã vạch pdf417 được tạo và lưu dưới dạng tệp PNG"}

## Bước 4: Ví dụ đầy đủ, có thể chạy được

Dưới đây là một ứng dụng console tự chứa, kết hợp tất cả các phần lại với nhau. Sao chép code vào một dự án `.csproj` mới và chạy — không cần file bổ sung nào.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

Chạy chương trình sẽ in ra một dòng xác nhận và tạo file PNG trong thư mục con `output`. Ảnh này có thể được nhúng vào báo cáo, in lên nhãn, hoặc gửi tới thiết bị di động để quét.

## Các biến thể phổ biến và trường hợp đặc biệt

| Kịch bản | Cần thay đổi | Lý do quan trọng |
|----------|--------------|-------------------|
| **Mã hoá chuỗi dài** | Tăng `Rows` hoặc để thư viện tự tính bằng cách bỏ qua việc gán `Rows` | PDF417 có thể chứa tới 1.850 ký tự; thiếu hàng sẽ gây cắt ngắn |
| **Chất lượng hình ảnh cao hơn** | Đặt `generator.Parameters.ImageResolution` thành 600 DPI | Hữu ích khi in trên máy in độ phân giải cao |
| **Định dạng ảnh khác** | Thay `BarCodeImageFormat.Png` bằng `Jpeg` hoặc `Tiff` | JPEG giảm kích thước file; TIFF giữ dữ liệu không mất mát cho lưu trữ |
| **Thêm vùng yên tĩnh** | `generator.Parameters.Barcode.XDimension = 2;` (hoặc điều chỉnh `Margins`) | Vùng yên tĩnh cải thiện độ tin cậy của máy quét trong môi trường ồn ào |
| **Văn bản động từ người dùng** | Thay chuỗi cứng bằng `Console.ReadLine()` | Cho phép tạo mã vạch tại thời gian chạy dựa trên dữ liệu người dùng |

### Cách tạo pdf417 barcode trong một Web API

Nếu bạn cần cung cấp chức năng tạo mã vạch qua endpoint ASP.NET Core, hãy trả về ảnh dưới dạng mảng byte:

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

Đoạn code này trả lời **cách tạo pdf417 barcode** ngay lập tức mà không cần ghi vào đĩa, rất phù hợp cho microservice hoặc backend di động.

## Kiểm thử mã vạch đã tạo

Để xác nhận mã vạch được tạo đúng:

1. Mở file PNG trong bất kỳ trình xem ảnh nào.  
2. Sử dụng một ứng dụng quét PDF417 miễn phí (ví dụ: ZXing, PDF417 Decoder) để quét ảnh.  
3. Xác nhận rằng văn bản giải mã khớp với đầu vào gốc.

Nếu trình quét báo lỗi, hãy kiểm tra lại giá trị cột/hàng và đảm bảo độ phân giải ảnh đủ cao cho thiết bị của bạn.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch pdf417** trong C# với kiểm soát đầy đủ các cột, hàng và định dạng đầu ra. Ví dụ đầy đủ minh họa toàn bộ quy trình — từ tạo `BarcodeGenerator` đến lưu file PNG — để bạn có thể tích hợp việc tạo mã vạch vào bất kỳ dự án .NET nào.

Tiếp theo, khám phá các chủ đề liên quan như **tối ưu bố cục pdf417 barcode**, nhúng mã vạch vào báo cáo PDF, hoặc giải mã mã vạch trên thiết bị di động. Điều chỉnh mức độ sửa lỗi và thử nghiệm các độ phân giải ảnh khác nhau sẽ giúp bạn tinh chỉnh giải pháp cho trường hợp sử dụng cụ thể. Chúc bạn lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ code hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}