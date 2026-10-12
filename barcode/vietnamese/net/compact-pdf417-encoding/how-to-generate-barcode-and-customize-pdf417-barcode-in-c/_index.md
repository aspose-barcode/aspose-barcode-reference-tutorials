---
category: general
date: 2026-09-19
description: Cách tạo mã vạch trong C# với hướng dẫn từng bước. Tìm hiểu cách tùy
  chỉnh cài đặt mã vạch PDF417 và tạo hình ảnh mã vạch mà các nhà phát triển C# có
  thể sử dụng ngay lập tức.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: vi
lastmod: 2026-09-19
og_description: Cách tạo mã vạch trong C# với hướng dẫn chi tiết. Tùy chỉnh các tham
  số mã vạch PDF417 và tạo hình ảnh mã vạch cho các dự án C# có thể sử dụng ngay hôm
  nay.
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: Cách tạo mã vạch và tùy chỉnh mã PDF417 trong C#
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: Cách tạo mã vạch và tùy chỉnh mã PDF417 trong C#
url: /vi/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch và tùy chỉnh mã PDF417 trong C#

Nếu bạn cần **cách tạo mã vạch** trong một ứng dụng .NET, hướng dẫn này sẽ cung cấp cho bạn một giải pháp hoàn chỉnh, sẵn sàng chạy. Bạn sẽ học cách tùy chỉnh kích thước mã PDF417, chọn số cột, và cuối cùng **tạo ảnh mã vạch C#** để các dự án có thể nhúng trực tiếp.

Việc tạo mã vạch không đòi hỏi một quy trình xây dựng phức tạp. Khi hoàn thành hướng dẫn này, bạn sẽ có một tệp PNG chứa mã MicroPDF417 có kích thước và độ phân giải chính xác mà bạn cần.

## Yêu cầu trước

Bạn nên cài đặt các thành phần sau trước khi bắt đầu:

* .NET 6.0 SDK hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.6+)
* Visual Studio 2022 (hoặc bất kỳ trình chỉnh sửa C# nào bạn thích)
* Gói NuGet Aspose.BarCode for .NET – cài đặt bằng  
  `dotnet add package Aspose.BarCode`

Không cần công cụ bên ngoài nào khác.

## Bước 1: Thiết lập dự án và nhập không gian tên

Tạo một dự án console mới và thêm tham chiếu tới Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Mở `Program.cs` và thêm các chỉ thị `using` cần thiết:

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

Các không gian tên này cung cấp các lớp cho phép bạn **cách tạo mã vạch** và điều khiển các tùy chọn đặc thù của PDF417.

## Bước 2: Khởi tạo trình tạo MicroPDF417 với văn bản mong muốn

Dòng đầu tiên tạo một thể hiện `BarcodeGenerator` được cấu hình cho ký hiệu MicroPDF417. Hàm khởi tạo nhận loại mã hoá và chuỗi dữ liệu bạn muốn mã hoá.

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**Tại sao lại quan trọng:** MicroPDF417 là một biến thể gọn gàng của chuẩn PDF417 đầy đủ, lý tưởng cho nhãn nhỏ hoặc màn hình di động. Khởi tạo trình tạo với `EncodeTypes` đúng đảm bảo thư viện sử dụng thuật toán mã hoá phù hợp.

## Bước 3: Tùy chỉnh kích thước X‑dimension (độ rộng mô-đun) để có độ phân giải mịn hơn

X‑dimension kiểm soát độ rộng của một mô-đun mã vạch (vạch đen hoặc trắng nhỏ nhất). Đặt giá trị pixel thấp sẽ tạo ra hình ảnh có độ phân giải cao hơn.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tại sao lại quan trọng:** X‑dimension lớn hơn giúp máy quét độ phân giải thấp đọc dễ dàng hơn, trong khi giá trị nhỏ hơn cho phép nén nhiều dữ liệu hơn trong không gian hạn chế. Điều chỉnh giá trị này dựa trên môi trường quét.

## Bước 4: Xác định số cột để kiểm soát kích thước mã vạch

MicroPDF417 cho phép 1‑4 cột. Nhiều cột tạo ra mã vạch ngắn, rộng; ít cột tạo ra mã vạch cao, hẹp.

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Tại sao lại quan trọng:** Lựa chọn số cột phù hợp giúp bạn đặt mã vạch vào một thành phần UI hoặc nhãn in cụ thể mà không cần phải thu phóng thủ công.

## Bước 5: Lưu mã vạch dưới dạng ảnh PNG

Cuối cùng, ghi mã vạch đã tạo ra lên đĩa. PNG giữ chất lượng không mất dữ liệu, rất quan trọng cho việc quét sắc nét.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Nếu thư mục đích không tồn tại, phương thức `Save` sẽ ném `ArgumentException`. Bạn có thể kiểm tra trước bằng một đoạn mã đơn giản:

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### Mã nguồn đầy đủ

Kết hợp các phần lại, đây là chương trình hoàn chỉnh, có thể chạy được:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Chạy chương trình này sẽ tạo ra một tệp có tên **MicroPdf417.png** trông giống như ảnh chụp màn hình dưới đây (ảnh đã được bỏ để ngắn gọn). Mã vạch mã hoá văn bản *Sample* và tuân theo các thiết lập X‑dimension và số cột mà bạn đã định nghĩa.

## Tùy chỉnh các tùy chọn PDF417 khác

Mặc dù hướng dẫn này tập trung vào **tùy chỉnh pdf417 barcode** các tham số ảnh hưởng đến kích thước, Aspose.BarCode còn cung cấp nhiều cài đặt bổ sung mà bạn có thể cần:

| Thuộc tính | Mục đích | Giá trị điển hình |
|------------|----------|-------------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | Điều khiển số hàng (chiều cao) | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | Đặt mức sửa lỗi (cao hơn = chịu lỗi tốt hơn) | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | Tạo mã vạch rút gọn (không có mẫu dừng) | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | Chọn nén số, văn bản hoặc byte | `CompactionModes.Numeric`, v.v. |

**Mẹo chuyên nghiệp:** Khi bạn cần một mã vạch vừa với chiều rộng cố định, hãy bắt đầu bằng cách tăng `Columns` và giảm `XDimension`. Nếu máy quét báo thiếu ký tự, hãy tăng `ErrorLevel` để cải thiện độ dư thừa.

## Xử lý các trường hợp đặc biệt

* **Văn bản quá dài cho MicroPDF417:** Biến thể Micro hỗ trợ tối đa 1 KB dữ liệu. Nếu chuỗi của bạn vượt quá giới hạn này, hãy chuyển sang ký hiệu `Pdf417` đầy đủ bằng cách thay `EncodeTypes.MicroPdf417` thành `EncodeTypes.Pdf417`.
* **Định dạng ảnh không được hỗ trợ:** `BarCodeImageFormat` cũng hỗ trợ `Jpeg`, `Bmp` và `Gif`. Chọn định dạng phù hợp với quy trình xử lý downstream của bạn.
* **Đường dẫn đa nền tảng:** Sử dụng `Path.Combine` thay vì dấu gạch chéo ngược cố định khi nhắm tới Linux hoặc macOS.

## Kiểm tra mã vạch

Bạn có thể kiểm tra hình ảnh đã tạo bằng bất kỳ ứng dụng quét mã vạch tiêu chuẩn nào (di động hoặc máy tính). Ứng dụng quét nên trả về văn bản gốc **Sample**. Nếu không:

1. Kiểm tra xem X‑dimension có được đặt dưới 1 pixel không (một số máy quét không thể phân giải mô-đun dưới pixel).
2. Đảm bảo tệp đầu ra không bị hỏng — chạy lại chương trình và so sánh kích thước tệp.
3. Tăng `ErrorLevel` để cải thiện khả năng chịu lỗi.

## Kết luận

Bây giờ bạn đã biết **cách tạo mã vạch** trong C# bằng Aspose.BarCode, cách **tùy chỉnh pdf417 barcode** kích thước và số cột, và cách **tạo ảnh mã vạch C#** để các dự án có thể nhúng trực tiếp. Ví dụ hoàn chỉnh minh họa quy trình thực tế từ thiết lập dự án đến xuất PNG cuối cùng.

Tiếp theo, khám phá các ký hiệu khác như QR, Code128, hoặc DataMatrix bằng cách thay đổi giá trị enum `EncodeTypes`. Điều chỉnh các tham số bổ sung như `Resolution` hoặc `Margin` cho phép bạn tinh chỉnh mọi mã vạch cho ứng dụng cụ thể của mình.

Chúc lập trình vui vẻ, và hãy để các mã vạch của bạn nâng tầm dự án tự động hoá tiếp theo!

## Bạn Nên Học Gì Tiếp Theo?


Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}