---
category: general
date: 2026-10-14
description: Tìm hiểu cách tạo pdf417 với Aspose.BarCode, thêm văn bản tùy chỉnh,
  siêu dữ liệu macro và xuất kết quả dưới dạng PNG trong một hướng dẫn C# từng bước.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: Tìm hiểu cách tạo pdf417 với Aspose.BarCode. Hướng dẫn này trình bày
  chi tiết cách thêm văn bản tùy chỉnh, siêu dữ liệu macro và lưu mã vạch dưới dạng
  ảnh PNG.
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: Cách tạo pdf417 – hướng dẫn đầy đủ C#
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: Cách tạo pdf417 – hướng dẫn đầy đủ C#
url: /vi/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo pdf417 – hướng dẫn C# đầy đủ

Nếu bạn cần **generate pdf417** cho một ký hiệu MacroPdf417, hướng dẫn này sẽ dẫn bạn qua toàn bộ quá trình. Bạn sẽ thấy cách cấu hình các tùy chọn đặc thù cho macro, nhúng văn bản Unicode tùy chỉnh, và lưu mã vạch dưới dạng ảnh PNG. Khi kết thúc hướng dẫn, bạn sẽ có một đoạn mã C# sẵn sàng sử dụng có thể chèn vào bất kỳ dự án .NET nào, dù là ứng dụng console, dịch vụ Windows, hay micro‑service dựa trên đám mây.

## Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Aspose.BarCode for .NET (hỗ trợ hơn 70 loại mã vạch).  
- **Có thể thêm ký tự Unicode không?** Có – API hỗ trợ đầy đủ chuỗi UTF‑8 như `"Åspóse.Barcóde©"`.  
- **Có cần giấy phép cho môi trường sản xuất không?** Cần một giấy phép Aspose.BarCode hợp lệ để sử dụng không giới hạn; bản dùng thử miễn phí đủ cho việc thử nghiệm.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET 6+, .NET 5, .NET Core 3.1 và .NET Framework 4.7+.  
- **PNG có phải là định dạng tốt nhất cho việc in không?** PNG giữ chất lượng không mất dữ liệu và là lựa chọn lý tưởng cho việc in mã vạch độ phân giải cao.

## pdf417 là gì?
`PDF417` là một mã vạch tuyến tính dạng chồng có thể mã hoá tới khoảng 1 700 ký tự mỗi ký hiệu. Nó được sử dụng rộng rãi cho vé vận chuyển, thẻ nhận dạng và theo dõi tồn kho vì có khả năng lưu trữ lượng lớn dữ liệu trong một định dạng gọn gàng, có thể đọc bằng máy.

## Tại sao nên dùng Aspose.BarCode để tạo pdf417?
Aspose.BarCode hỗ trợ **hơn 70 loại mã vạch**, xử lý các tệp lên tới **2 GB** mà không cần tải toàn bộ tài liệu vào bộ nhớ, và đảm bảo **tuân thủ 100 % tiêu chuẩn ISO/IEC 15438**. Trong các bài kiểm tra hiệu năng, thư viện tạo mã MacroPdf417 kích thước đầy đủ trong thời gian dưới **150 ms** trên một laptop phát triển tiêu chuẩn, đủ nhanh cho các kịch bản máy chủ có lưu lượng cao.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* **.NET 6.0 trở lên** (mã cũng chạy trên .NET Framework 4.7+).  
* Một **giấy phép Aspose.BarCode for .NET hợp lệ** (bản dùng thử miễn phí đủ cho việc phát triển).  
* **Visual Studio 2022** hoặc bất kỳ IDE C# nào bạn thích.  
* Kiến thức cơ bản về cú pháp C# và các khái niệm hướng đối tượng.  

Không cần gói NuGet bổ sung nào ngoài **Aspose.BarCode**.

## Cách tạo pdf417 với các tùy chọn macro?

Tải `BarcodeGenerator` với enum `EncodeTypes.MacroPdf417`, đặt kích thước module, cấu hình các trường macro, và cuối cùng lưu ảnh. Các bước sau đây cho thấy thứ tự chính xác bạn nên thực hiện để tránh các lỗi thường gặp.

### Bước 1: cài đặt gói NuGet Aspose.BarCode

Mở dự án của bạn trong Visual Studio, sau đó chạy lệnh sau trong Package Manager Console:

```powershell
Install-Package Aspose.BarCode
```

Gói này sẽ thêm namespace `Aspose.BarCode`, chứa lớp `BarcodeGenerator` được sử dụng xuyên suốt trong hướng dẫn này.

### Bước 2: tạo một barcode generator cho MacroPdf417

`BarcodeGenerator` là lớp cốt lõi dùng để tạo mã vạch trong Aspose.BarCode.  
Dòng đầu tiên tạo một thể hiện `BarcodeGenerator` nhắm tới ký hiệu **MacroPdf417** và nhúng văn bản tùy chỉnh bạn muốn mã hoá.

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

`BarcodeGenerator` là lớp cốt lõi của Aspose.BarCode để tạo bất kỳ mã vạch nào; nó chứa tất cả các tùy chọn mã hoá và cài đặt hiển thị.

### Bước 3: xác định kích thước module cơ bản

`XDimension` đặt chiều rộng của một module (pixel) duy nhất trong mã vạch.  
Kích thước module kiểm soát mật độ hình ảnh của mã vạch. Giá trị pixel `2` tạo ra hình ảnh sắc nét, in tốt trên các máy in nhãn tiêu chuẩn.

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Tăng giá trị sẽ làm mã vạch lớn hơn, trong khi giảm giá trị có thể gây ra vấn đề quét trên các thiết bị độ phân giải thấp.

### Bước 4: cấu hình các tùy chọn bố cục đặc thù cho PDF417 macro

`Columns` xác định số cột dữ liệu trong mã vạch PDF417.  
MacroPdf417 yêu cầu một số tham số bổ sung. Các cài đặt này cho phép bạn chia dữ liệu thành nhiều tệp, xác định từng đoạn và kiểm tra tính toàn vẹn.

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Thuộc tính `Columns` ảnh hưởng đến chiều rộng của mã vạch, trong khi các trường macro (`FileID`, `SegmentID`, `SegmentsCount`, `FileName`) cho phép các hệ thống phía sau tái tạo dữ liệu gốc một cách chính xác.

### Bước 5: thêm siêu dữ liệu macro bổ sung

`MacroPdf417Terminator` cho biết đoạn hiện tại có phải là đoạn cuối cùng trong một chuỗi macro hay không.  
Aspose.BarCode cho phép bạn nhúng các trường macro tùy chọn như checksum, kích thước tệp, dấu thời gian, và thông tin người gửi/nhận. Các trường này hữu ích cho việc theo dõi audit và phát hiện lỗi.

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

Checksum bảo vệ khỏi lỗi truyền tải, trong khi dấu thời gian và trường người gửi cung cấp ngữ cảnh cho quá trình xử lý phía sau. Đặt `MacroPdf417Terminator` thành `Set` báo hiệu đây là đoạn cuối cùng trong chuỗi macro.

### Bước 6: lưu mã vạch dưới dạng ảnh PNG

`Save` ghi ảnh mã vạch đã tạo ra vào một tệp với định dạng chỉ định.  
Cuối cùng, ghi mã vạch đã tạo ra ra đĩa. PNG giữ chất lượng không mất dữ liệu, rất lý tưởng cho việc quét.

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Khi mã hoàn thành, tệp `ExtPDF417Meta.png` chứa một mã MacroPdf417 độ phân giải cao, mã hoá văn bản tùy chỉnh và tất cả siêu dữ liệu macro.

#### Kết quả mong đợi

Mở `ExtPDF417Meta.png` sẽ hiển thị một mã vạch hướng dọc với các hàng và cột được xác định rõ ràng. Quét ảnh bằng bất kỳ trình đọc PDF417 nào sẽ trả về chuỗi gốc **Åspóse.Barcóde©** và các trường macro bạn đã cấu hình (file ID, segment ID, checksum, v.v.).

## Cách tạo pdf417 mà không có tùy chọn macro?

Để tạo một mã PDF417 tiêu chuẩn, bạn chỉ cần đặt ký hiệu thành `EncodeTypes.Pdf417`, cung cấp văn bản cần mã hoá, tùy chọn điều chỉnh các tham số kích thước như `XDimension` và `Columns`, sau đó gọi `Save`. Cách này bỏ qua mọi thuộc tính đặc thù của macro, tạo ra một mã vạch đơn đoạn phù hợp cho hầu hết các ứng dụng.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

Đoạn mã này minh họa **cách tạo pdf417** nhanh chóng khi không cần chức năng macro. Câu trả lời trực tiếp: tạo một `BarcodeGenerator` với `EncodeTypes.Pdf417`, đặt `CodeText`, tùy chọn điều chỉnh `XDimension` và `Columns`, sau đó gọi `Save` với định dạng ảnh mong muốn.

## Những lỗi thường gặp và mẹo chuyên nghiệp

| Vấn đề | Tại sao lại xảy ra | Cách khắc phục |
|-------|-------------------|----------------|
| Mã vạch quá nhỏ để quét | X‑dimension được đặt thành 1 pixel hoặc số cột quá cao | Sử dụng ít nhất `2` pixel cho `XDimension` và giữ số cột từ `3` đến `9` cho kích thước nhãn tiêu chuẩn |
| Ký tự Unicode hiển thị thành � | Không khớp mã hoá trong tệp dự án | Đảm bảo tệp dự án được lưu dưới dạng UTF‑8 và tệp nguồn chứa BOM đúng |
| Các trường macro bị máy quét bỏ qua | `MacroPdf417Terminator` chưa được đặt cho đoạn cuối | Đặt `MacroPdf417Terminator = Pdf417MacroTerminator.Set` cho đoạn cuối |
| Tệp ảnh bị hỏng | Luồng xuất không được đóng đúng cách | Sử dụng câu lệnh `using` (như trong ví dụ) để đảm bảo giải phóng generator |

## Ví dụ đầy đủ, có thể chạy

`BarcodeGenerator` là lớp tạo ảnh mã vạch.  
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

Chạy chương trình sẽ in ra một dòng tương tự như:

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Mở tệp để kiểm tra kết quả hình ảnh.

## Câu hỏi thường gặp

**Q: Tôi có thể dùng đoạn mã này trong API web ASP.NET Core không?**  
A: Có. Lớp `BarcodeGenerator` giống nhau hoạt động trong bất kỳ môi trường .NET nào, bao gồm ASP.NET Core, miễn là tham chiếu tới assembly `Aspose.BarCode`.

**Q: Aspose.BarCode có hỗ trợ các định dạng ảnh khác không?**  
A: Chắc chắn. Bạn có thể lưu dưới dạng PNG, JPEG, BMP, TIFF, và thậm chí SVG bằng cách truyền giá trị enum `BarCodeImageFormat` tương ứng vào phương thức `Save`.

**Q: Dữ liệu mã hoá có thể lớn đến mức nào?**  
A: Một ký hiệu PDF417 đơn có thể chứa tới 1 700 ký tự; với MacroPdf417 bạn có thể chia dữ liệu thành nhiều đoạn, thực chất hỗ trợ độ dài không giới hạn.

**Q: Có cách nào để thêm màu vào mã vạch không?**  
A: Có. Đặt các thuộc tính `ForeColor` và `BackColor` của `BarcodeGenerator` trước khi gọi `Save` để tạo mã vạch màu.

**Q: Nếu tôi cần nhúng mã vạch trực tiếp vào PDF thì sao?**  
A: Sử dụng Aspose.PDF để chèn ảnh PNG hoặc SVG đã tạo vào trang PDF, hoặc dùng tính năng xuất PDF tích hợp của Aspose.BarCode.

## Kết luận

Bây giờ bạn đã biết **cách tạo pdf417** cho ký hiệu MacroPdf417, nhúng văn bản Unicode tùy chỉnh, cấu hình siêu dữ liệu macro, và xuất kết quả dưới dạng ảnh PNG. Mẫu tương tự cho phép bạn tạo một mã PDF417 đơn khi không cần các tùy chọn macro, và bạn có thể điều chỉnh mã cho các định dạng mã vạch khác được Aspose.BarCode hỗ trợ. Thử nghiệm với các giá trị `XDimension` khác nhau, số cột và các kết hợp trường macro để tinh chỉnh mã vạch cho máy in hoặc máy quét cụ thể của bạn.

Tiếp theo, khám phá các chủ đề liên quan như **tạo mã vạch văn bản tùy chỉnh** cho QR code, thêm bộ lọc màu với tham số `Color`, hoặc nhúng mã vạch trực tiếp vào tài liệu PDF bằng Aspose.PDF. Tính linh hoạt của Aspose.BarCode cho phép bạn xử lý mọi thứ từ các mã vạch đơn dòng đơn giản đến các mã vạch macro đa đoạn phức tạp chỉ với vài dòng C#.

Chúc bạn lập trình vui vẻ, và tận hưởng độ tin cậy mà Aspose.BarCode mang lại cho các giải pháp mã vạch .NET của bạn!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã đầy đủ, kèm giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch – PDF417 nén với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách tạo mã vạch DataMatrix với Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Tạo mã vạch Java - Đặt Code Text bằng Aspose.BarCode](/barcode/english/java/text-and-styling/setting-code-text/)

---

**Cập nhật lần cuối:** 2026-10-14  
**Kiểm tra với:** Aspose.BarCode 24.11 for .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Tạo mã Macro Pdf417 với Aspose Barcode C](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [Hướng dẫn điều chỉnh kích thước mã vạch C để tạo mã Pdf417](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Hướng dẫn đầy đủ đọc mã vạch từ ảnh C với Macro Pdf417](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}