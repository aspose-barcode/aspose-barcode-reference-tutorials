---
category: general
date: 2026-08-12
description: Tạo mã vạch Aspose với Aspose.BarCode và học cách tạo pdf417 với văn
  bản tùy chỉnh trong vài bước đơn giản.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode aspose
- how to generate pdf417
- create barcode custom text
- Aspose.BarCode macro pdf417
- barcode metadata Aspose
language: vi
lastmod: 2026-08-12
og_description: Tạo mã vạch Aspose bằng Aspose.BarCode. Hướng dẫn này cho thấy cách
  tạo pdf417 với văn bản tùy chỉnh, siêu dữ liệu macro và lưu kết quả dưới dạng PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Tạo mã vạch Aspose – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Generate barcode aspose with Aspose.BarCode and learn how to generate
    pdf417 with custom text in a few easy steps.
  headline: Generate barcode aspose – complete C# guide
  type: TechArticle
tags:
- Aspose
- barcode
- pdf417
title: Tạo mã vạch Aspose – hướng dẫn C# đầy đủ
url: /vi/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch aspose – hướng dẫn đầy đủ C# 

Nếu bạn cần **generate barcode aspose** cho ký hiệu MacroPdf417, hướng dẫn này sẽ đưa bạn qua toàn bộ quá trình. Bạn sẽ thấy cách cấu hình các tùy chọn đặc thù cho macro, nhúng văn bản tùy chỉnh, và lưu mã vạch dưới dạng ảnh PNG.

Việc tạo mã vạch với Aspose.BarCode loại bỏ việc tính toán thủ công và đảm bảo tuân thủ chuẩn PDF417. Trong các bước dưới đây, bạn cũng sẽ học **how to generate pdf417** với siêu dữ liệu tùy chỉnh như ID tệp, số đoạn và dấu thời gian. Khi kết thúc hướng dẫn, bạn sẽ có một mẫu mã sẵn sàng sử dụng mà có thể chèn vào bất kỳ dự án .NET nào.

## Yêu cầu trước

* .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+)
* Giấy phép Aspose.BarCode cho .NET hợp lệ (phiên bản dùng thử miễn phí hoạt động cho việc thử nghiệm)
* Visual Studio 2022 hoặc bất kỳ IDE C# nào bạn thích
* Kiến thức cơ bản về cú pháp C# và các khái niệm hướng đối tượng

Không cần thêm bất kỳ gói NuGet nào ngoài **Aspose.BarCode**.

## Bước 1: Cài đặt gói NuGet Aspose.BarCode

Mở dự án của bạn trong Visual Studio, sau đó chạy lệnh sau trong Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Gói này sẽ thêm namespace `Aspose.BarCode`, chứa lớp `BarcodeGenerator` được sử dụng xuyên suốt trong hướng dẫn này.

## Bước 2: Tạo trình tạo mã vạch cho MacroPdf417

Dòng đầu tiên tạo một thể hiện `BarcodeGenerator` nhắm tới ký hiệu **MacroPdf417** và nhúng văn bản tùy chỉnh mà bạn muốn mã hoá.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

*Tiêu đề quan trọng*: Enum `EncodeTypes.MacroPdf417` cho Aspose biết rằng mã vạch sẽ được xem như một ký hiệu PDF417 có hỗ trợ macro, cho phép chia dữ liệu lớn thành nhiều đoạn. Chuỗi `"Åspóse.Barcóde©"` minh họa rằng trình tạo xử lý đúng các ký tự Unicode.

## Bước 3: Định nghĩa kích thước mô-đun cơ bản

Kích thước mô-đun kiểm soát mật độ hiển thị của mã vạch. Giá trị pixel `2` tạo ra hình ảnh sắc nét, in tốt trên các máy in nhãn tiêu chuẩn.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Tăng giá trị sẽ làm mã vạch lớn hơn, trong khi giảm giá trị có thể gây ra vấn đề quét trên các thiết bị độ phân giải thấp.

## Bước 4: Cấu hình các tùy chọn bố cục đặc thù cho macro PDF417

MacroPdf417 yêu cầu một số tham số bổ sung. Các cài đặt này cho phép bạn chia dữ liệu thành nhiều tệp, xác định từng đoạn và kiểm tra tính toàn vẹn.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

*Tiêu đề quan trọng*: Thuộc tính `Columns` ảnh hưởng đến chiều rộng của mã vạch, trong khi các trường macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) cho phép các hệ thống phía sau tái tạo lại dữ liệu gốc một cách chính xác.

## Bước 5: Thêm siêu dữ liệu macro bổ sung

Aspose.BarCode cho phép bạn nhúng các trường macro tùy chọn như checksum, kích thước tệp, dấu thời gian và thông tin người gửi/nhận. Các trường này hữu ích cho việc theo dõi audit và phát hiện lỗi.

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

*Tiêu đề quan trọng*: Checksum bảo vệ khỏi lỗi truyền, trong khi dấu thời gian và trường người gửi cung cấp ngữ cảnh cho quá trình xử lý phía sau. Đặt `MacroPdf417Terminator` thành `Set` báo hiệu đây là đoạn cuối cùng trong chuỗi macro.

## Bước 6: Lưu mã vạch dưới dạng ảnh PNG

Cuối cùng, ghi mã vạch đã tạo ra lên đĩa. PNG giữ chất lượng không mất dữ liệu, rất lý tưởng cho việc quét.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Khi mã hoàn thành, tệp `ExtPDF417Meta.png` chứa một mã vạch MacroPdf417 độ phân giải cao, mã hoá văn bản tùy chỉnh và tất cả siêu dữ liệu macro.

### Kết quả mong đợi

Mở `ExtPDF417Meta.png` sẽ hiển thị một mã vạch dọc với các hàng và cột được xác định rõ ràng. Quét ảnh bằng bất kỳ trình đọc PDF417 nào sẽ trả về chuỗi gốc **Åspóse.Barcóde©** và các trường macro bạn đã cấu hình (ID tệp, ID đoạn, checksum, v.v.).

## Cách tạo pdf417 mà không có tùy chọn macro (kịch bản thay thế)

Nếu bạn chỉ cần một mã vạch PDF417 tiêu chuẩn, bỏ qua các thuộc tính macro và giữ cấu hình cơ bản:

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Đoạn mã này minh họa **how to generate pdf417** nhanh chóng khi không cần chức năng macro.

## Những lỗi thường gặp và mẹo chuyên nghiệp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| Mã vạch quá nhỏ để quét | X‑dimension được đặt thành 1 pixel hoặc số cột quá cao | Sử dụng ít nhất `2` pixel cho `XDimension` và giữ số cột từ `3` đến `9` cho kích thước nhãn tiêu chuẩn |
| Ký tự Unicode hiển thị thành � | Không khớp mã hoá trong tệp dự án | Đảm bảo tệp dự án được lưu dưới dạng UTF‑8 và tệp nguồn chứa BOM đúng |
| Các trường macro bị máy quét bỏ qua | `MacroPdf417Terminator` không được đặt cho đoạn cuối | Đặt `MacroPdf417Terminator = Pdf417MacroTerminator.Set` cho đoạn cuối cùng |
| Tệp ảnh bị hỏng | Luồng xuất không được đóng đúng cách | Sử dụng câu lệnh `using` (như trong ví dụ) để đảm bảo giải phóng trình tạo |

## Ví dụ đầy đủ, có thể chạy

Sao chép đoạn mã dưới đây vào một ứng dụng console mới và chạy nó. Chương trình sẽ tạo mã vạch, lưu lại và in đường dẫn đầu ra ra console.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

Chạy chương trình sẽ in ra một dòng tương tự:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Mở tệp để xác nhận kết quả hình ảnh.

## Kết luận

Bây giờ bạn đã biết cách **generate barcode aspose** cho ký hiệu MacroPdf417, nhúng văn bản Unicode tùy chỉnh, cấu hình siêu dữ liệu macro và xuất kết quả dưới dạng ảnh PNG. Mẫu tương tự cho phép bạn **how to generate pdf417** mà không cần tùy chọn macro, và bạn có thể điều chỉnh mã cho các định dạng mã vạch khác được Aspose.BarCode hỗ trợ.

Tiếp theo, khám phá các chủ đề liên quan như **create barcode custom text** cho mã QR, thêm bộ lọc màu với các tham số `Color`, hoặc nhúng mã vạch trực tiếp vào tài liệu PDF bằng Aspose.PDF. Thử nghiệm với các giá trị `XDimension` và số cột khác nhau để tinh chỉnh mã vạch cho máy in hoặc máy quét cụ thể của bạn.

Chúc lập trình vui vẻ, và tận hưởng độ tin cậy mà Aspose.BarCode mang lại cho các giải pháp mã vạch .NET của bạn!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoàn chỉnh kèm giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch – PDF417 Compact với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách tạo mã DataMatrix với Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Tạo mã vạch Java - Đặt văn bản mã bằng Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}