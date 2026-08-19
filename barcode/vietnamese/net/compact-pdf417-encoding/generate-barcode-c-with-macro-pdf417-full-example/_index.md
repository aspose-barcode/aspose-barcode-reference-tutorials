---
category: general
date: 2026-08-19
description: Tạo mã vạch C# bằng Aspose.BarCode để tạo Macro PDF417 với văn bản tùy
  chỉnh và lưu dưới dạng tệp hình ảnh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode C#
- how to generate pdf417
- create barcode custom text
- generate barcode image file
language: vi
lastmod: 2026-08-19
og_description: Tạo mã vạch C# với Aspose.BarCode, tìm hiểu cách tạo PDF417, thêm
  văn bản tùy chỉnh và lưu tệp hình ảnh mã vạch.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Tạo mã vạch C# – Hướng dẫn Macro PDF417
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate barcode C# using Aspose.BarCode to create a Macro PDF417 with
    custom text and save as an image file.
  headline: Generate barcode C# with Macro PDF417 – full example
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif` as
      needed.
    question: Can I generate a different image format?
  - answer: Macro PDF417 is designed for segmentation. Adjust `MacroPdf417SegmentsCount`
      and `MacroPdf417SegmentID` for each part, then concatenate the scanned results.
    question: What if my data exceeds a single barcode?
  - answer: Aspose.BarCode fully supports Unicode. Ensure your source file is saved
      with UTF‑8 encoding to avoid character corruption.
    question: Is Unicode support guaranteed?
  - answer: A licensed version removes the evaluation watermark and provides full
      functionality. The trial works for testing and learning.
    question: Do I need a license for production?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: Tạo mã vạch C# với Macro PDF417 – ví dụ đầy đủ
url: /vi/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch C# với Macro PDF417 – ví dụ đầy đủ

Nếu bạn cần **tạo mã vạch C#** cho định dạng Macro PDF417, hướng dẫn này sẽ cung cấp cho bạn một giải pháp sẵn sàng chạy. Bạn sẽ thấy cách **tạo pdf417**, nhúng văn bản tùy chỉnh, và **tạo file ảnh mã vạch** trong một chương trình tự chứa duy nhất.

Bài học bao gồm mọi thứ từ cài đặt thư viện Aspose.BarCode đến cấu hình siêu dữ liệu Macro PDF417, vì vậy bạn có thể sao chép mã trực tiếp vào dự án và thấy kết quả ngay lập tức.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- .NET 6.0 SDK hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+)
- Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ C#)
- Giấy phép Aspose.BarCode for .NET (bản dùng thử miễn phí đủ cho việc đánh giá)
- Kiến thức cơ bản về cú pháp C#

> **Mẹo chuyên nghiệp:** Cài đặt gói NuGet qua CLI để tránh xung đột phiên bản:  
> `dotnet add package Aspose.BarCode`

## Bước 1: Thiết lập dự án và nhập thư viện

Tạo một ứng dụng console mới và thêm các chỉ thị `using` cần thiết.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The full barcode generation logic starts in the next step.
        }
    }
}
```

**Tại sao bước này quan trọng:**  
Namespace `Aspose.BarCode.Generation` cung cấp lớp `BarcodeGenerator`, là điểm vào để tạo bất kỳ loại mã vạch nào, bao gồm Macro PDF417. Nhập `System` cho phép bạn truy cập `DateTime` để thêm siêu dữ liệu thời gian.

## Bước 2: Tạo trình tạo Macro PDF417 với văn bản tùy chỉnh

Thay thế chú thích placeholder bằng việc khởi tạo trình tạo. Điều này minh họa **tạo mã vạch văn bản tùy chỉnh** đồng thời chọn kiểu mã hoá đúng.

```csharp
// Step 2: Initialize a barcode generator for Macro PDF417 with custom text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,          // Choose Macro PDF417 as the symbology
    "Åspóse.Barcóde©");               // Custom text can contain Unicode characters
```

**Giải thích:**  
- `EncodeTypes.MacroPdf417` báo cho Aspose tạo mã vạch PDF417 hỗ trợ các tính năng macro (phân đoạn tệp, checksum, v.v.).  
- Văn bản `"Åspóse.Barcóde©"` cho thấy các ký tự Unicode được hỗ trợ hoàn toàn, thường cần cho các ứng dụng quốc tế.

## Bước 3: Cấu hình giao diện và siêu dữ liệu Macro PDF417

Tinh chỉnh kích thước mã vạch và đặt các trường đặc thù cho macro cần thiết cho việc xử lý tệp phân đoạn.

```csharp
// Appearance: set the narrow bar width to 2 pixels.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// PDF417 specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;  // Total number of segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 CRC checksum
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;   // Approximate file size in bytes
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Tại sao các thiết lập này quan trọng:**

| Cài đặt | Mục đích |
|---------|----------|
| `XDimension.Pixels` | Kiểm soát mật độ hình ảnh; 2 px tạo ra hình ảnh rõ ràng, dễ quét. |
| `Columns` | Xác định số cột dữ liệu xuất hiện trên mỗi hàng, ảnh hưởng đến kích thước mã vạch. |
| `MacroPdf417FileID` | Định danh duy nhất tệp logic trên tất cả các đoạn. |
| `MacroPdf417SegmentID` / `SegmentsCount` | Cho phép tái tạo tệp gốc từ nhiều mã vạch. |
| `MacroPdf417FileName` | Tên đọc được lưu trong mã vạch để xử lý tiếp theo. |
| `MacroPdf417Checksum` | Cung cấp phát hiện lỗi bằng thuật toán CRC CCITT‑16. |
| `MacroPdf417FileSize` | Giúp bộ giải mã biết khi nào đã nhận đủ toàn bộ tệp. |
| `MacroPdf417TimeStamp` | Ghi lại thời điểm mã vạch được tạo, hữu ích cho truy vết. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Các trường tùy chọn có thể được dùng trong quy trình kinh doanh. |
| `MacroPdf417Terminator` | Chỉ ra rằng đoạn này là đoạn cuối cùng (`Set`). |

## Bước 4: Lưu mã vạch dưới dạng file ảnh

Cuối cùng, ghi mã vạch ra file PNG để bạn có thể xem hoặc nhúng vào nơi khác.

```csharp
// Step 4: Save the generated barcode image to a file.
string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";   // Adjust the folder as needed
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

**Bạn sẽ thấy:**  
Một ảnh PNG có tên `ExtPDF417Meta.png` chứa mã vạch Macro PDF417 mã hoá văn bản tùy chỉnh và tất cả các trường siêu dữ liệu bạn đã thiết lập ở trên. Ảnh có thể mở bằng bất kỳ trình xem tiêu chuẩn nào hoặc chèn vào PDF, báo cáo, hoặc trang web.

## Mã nguồn đầy đủ (sẵn sàng sao chép)

```csharp
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with custom Unicode text.
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.MacroPdf417,
                "Åspóse.Barcóde©");

            // Appearance settings.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Macro PDF417 metadata.
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the barcode image.
            string outputPath = @"C:\Barcodes\ExtPDF417Meta.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Kết quả mong đợi

Chạy chương trình sẽ in ra:

```
Barcode saved to C:\Barcodes\ExtPDF417Meta.png
```

Mở `ExtPDF417Meta.png` sẽ hiển thị một mã vạch Macro PDF417 sạch sẽ, quét đúng với bất kỳ trình đọc PDF417 nào, giữ nguyên văn bản tùy chỉnh `"Åspóse.Barcóde©"` và siêu dữ liệu macro bạn đã định nghĩa.

## Các câu hỏi thường gặp và trường hợp đặc biệt

- **Tôi có thể tạo định dạng ảnh khác không?**  
  Có. Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, hoặc `Gif` tùy nhu cầu.

- **Nếu dữ liệu của tôi vượt quá một mã vạch thì sao?**  
  Macro PDF417 được thiết kế cho phân đoạn. Điều chỉnh `MacroPdf417SegmentsCount` và `MacroPdf417SegmentID` cho mỗi phần, sau đó nối các kết quả quét lại.

- **Unicode có được hỗ trợ chắc chắn không?**  
  Aspose.BarCode hỗ trợ Unicode hoàn toàn. Đảm bảo file nguồn của bạn được lưu với mã hoá UTF‑8 để tránh hỏng ký tự.

- **Tôi có cần giấy phép cho môi trường production không?**  
  Phiên bản có giấy phép loại bỏ watermark đánh giá và cung cấp đầy đủ chức năng. Bản dùng thử đủ cho việc thử nghiệm và học tập.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch C#** cho Macro PDF417, **tạo pdf417** với siêu dữ liệu phong phú, **tạo mã vạch văn bản tùy chỉnh**, và **tạo file ảnh mã vạch** bằng Aspose.BarCode. Ví dụ hoàn chỉnh, có thể chạy ngay này minh họa mọi bước cần thiết—from thiết lập dự án đến lưu ảnh PNG cuối cùng.

### Các bước tiếp theo

- Thử nghiệm các thiết lập PDF417 khác như `ErrorCorrectionLevel` và `CompactPdf417` để có ký hiệu nhỏ hơn.  
- Tích hợp mã vạch đã tạo vào báo cáo PDF bằng Aspose.PDF.  
- Khám phá tạo hàng loạt: lặp qua một tập hợp tệp và tạo một loạt mã vạch Macro PDF417 phân đoạn.

Hãy tự do điều chỉnh mã cho quy trình của bạn, và để việc tạo mã vạch trở thành một phần liền mạch trong các ứng dụng C# của bạn. Chúc lập trình vui!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch Aztec với tỷ lệ khung tùy chỉnh bằng Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Tạo ảnh mã vạch – Code 93 với Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [Cách tạo và điều chỉnh chiều cao mã vạch One-Dimensional Databar bằng Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}