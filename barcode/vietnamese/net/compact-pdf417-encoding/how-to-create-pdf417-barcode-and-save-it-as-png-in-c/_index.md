---
category: general
date: 2026-10-05
description: Tìm hiểu cách tạo mã vạch PDF417 bằng C# và tạo ảnh PNG cho mã vạch với
  hướng dẫn code từng bước và các mẹo thực hành tốt nhất.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: vi
lastmod: 2026-10-05
og_description: Tạo mã vạch PDF417 bằng C# và tạo ngay PNG cho mã vạch. Theo dõi hướng
  dẫn đầy đủ này để có giải pháp sẵn sàng cho sản xuất.
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: Tạo mã vạch PDF417 trong C# – hướng dẫn đầy đủ để tạo PNG
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: Cách tạo mã vạch PDF417 và lưu dưới dạng PNG trong C#
url: /vi/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 và lưu dưới dạng PNG trong C#

Nếu bạn cần **tạo mã vạch PDF417** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chi tiết. Bạn sẽ nhận được một đoạn mã C# sẵn sàng sử dụng để tạo ra tệp **barcode PNG** chất lượng cao, và bạn sẽ hiểu mọi cài đặt ảnh hưởng đến kết quả.

Việc tạo mã vạch là yêu cầu phổ biến cho các hệ thống bán vé, theo dõi tồn kho và mã hoá tài liệu bảo mật. Khi kết thúc tutorial này, bạn có thể trả lời câu hỏi “**cách tạo PDF417**” bằng một ví dụ hoàn chỉnh, có thể chạy được.

## Yêu cầu trước

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Môi trường phát triển như Visual Studio 2022 hoặc VS Code  
* Gói NuGet **Aspose.BarCode for .NET** (hoặc bất kỳ thư viện tương thích nào hỗ trợ PDF417)  

Bạn có thể thêm gói bằng lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

Đoạn mã dưới đây sử dụng Aspose API vì nó cung cấp khả năng kiểm soát chi tiết các tham số PDF417 và hỗ trợ xuất PNG ngay từ đầu.

## Bước 1: Thiết lập dự án và nhập các namespace

Tạo một dự án console mới và nhập các namespace cần thiết:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Namespace `Aspose.BarCode.Generation` chứa lớp `BarcodeGenerator`, là điểm khởi đầu để **tạo hình ảnh mã vạch PDF417**.

## Bước 2: Tạo mã vạch PDF417 với văn bản mong muốn

Khởi tạo generator với enum `EncodeTypes.Pdf417` và dữ liệu bạn muốn mã hoá. Ví dụ sử dụng một chuỗi chứa các ký tự đặc biệt để minh họa việc xử lý Unicode:

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Generator hiện đang chứa một đối tượng barcode mà bạn có thể cấu hình trước khi render.

## Bước 3: Cấu hình các tham số hiển thị

Tinh chỉnh mã vạch giúp cải thiện khả năng đọc và giảm kích thước ảnh. Các cài đặt thường được điều chỉnh nhất là **X‑dimension**, **columns**, và **compact mode**.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** kiểm soát độ rộng của mỗi mô-đun; giá trị `2` pixel tạo ra một mã vạch gọn gàng nhưng vẫn dễ đọc.  
* **Columns** xác định số cột dữ liệu mà mã sử dụng. Ít cột hơn sẽ làm mã vạch hẹp hơn nhưng cao hơn.  
* **Truncate** kích hoạt chế độ “compact” theo đặc tả PDF417, loại bỏ các hàng đệm không cần thiết.  

Bạn có thể thử nghiệm với `Rows` và `ErrorCorrectionLevel` nếu trường hợp sử dụng của bạn yêu cầu độ chịu lỗi cao hơn.

## Bước 4: Lưu mã vạch dưới dạng ảnh PNG

Cuối cùng, xuất mã vạch ra tệp PNG. PNG giữ được các cạnh sắc nét và hỗ trợ trong suốt, rất phù hợp cho các kịch bản web và in ấn.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Chạy chương trình sẽ tạo ra tệp `CompactPdf417.png` trong thư mục đã chỉ định. Hình ảnh trông như sau:

![Mã vạch PDF417 gọn được tạo bằng C#](compact-pdf417.png "Ví dụ về mã vạch PDF417 gọn được tạo bằng C#")

*Văn bản thay thế (alt text) ở trên chứa từ khóa chính, đáp ứng cả yêu cầu SEO và khả năng truy cập.*

## Ví dụ đầy đủ, có thể chạy

Kết hợp tất cả các phần lại, dưới đây là một chương trình tự chứa mà bạn có thể sao chép, dán và chạy:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### Kết quả mong đợi

Khi mở `CompactPdf417.png`, bạn sẽ thấy một mã vạch dọc, mật độ cao mã hoá chuỗi *Åspóse.Barcóde©*. Quét ảnh bằng bất kỳ trình đọc PDF417 nào sẽ trả về lại văn bản gốc.

## Tại sao các cài đặt này lại quan trọng

* **X‑dimension** ảnh hưởng đến cả kích thước vật lý và tốc độ quét. Các mô-đun nhỏ hơn tăng mật độ dữ liệu nhưng có thể yêu cầu máy quét độ phân giải cao hơn.  
* **Columns** ảnh hưởng đến tỉ lệ khung hình. Đối với biên lai di động, số cột thấp giúp mã vạch đủ hẹp để vừa trên giấy hẹp.  
* **Truncate** giảm số hàng, tiết kiệm mực và không gian mà không làm mất tính toàn vẹn dữ liệu, vì PDF417 đã bao gồm các mã sửa lỗi.  

Hiểu các tham số này cho phép bạn tùy chỉnh mã vạch phù hợp với các hạn chế của phương tiện mục tiêu — dù là máy in nhãn, trang web, hay ứng dụng di động.

## Các biến thể phổ biến và trường hợp đặc biệt

### Tạo các định dạng ảnh khác

Nếu bạn muốn JPEG hoặc BMP, thay đổi enum `BarCodeImageFormat`:

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG nén ảnh nhưng có thể tạo ra các artefact ảnh hưởng đến việc quét ở kích thước nhỏ.

### Điều chỉnh mức sửa lỗi

Đối với môi trường khắc nghiệt (ví dụ: biển hiệu ngoài trời), tăng mức sửa lỗi:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

Mức cao hơn thêm nhiều dư thừa, làm mã vạch lớn hơn nhưng bền hơn.

### Mã hoá dữ liệu nhị phân

PDF417 có thể mã hoá dữ liệu nhị phân. Truyền một `byte[]` thay vì chuỗi:

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

Thư viện sẽ tự động chuyển sang chế độ nhị phân.

### Xử lý chuỗi rất dài

Khi dữ liệu vượt quá dung lượng mặc định, generator sẽ tự động tạo thêm các hàng. Bạn có thể giới hạn số hàng để tránh ảnh quá lớn:

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

Nếu nội dung vẫn không vừa, hãy cân nhắc chia nó thành nhiều mã vạch.

## Mẹo chuyên nghiệp

* **Cache generator** nếu bạn cần tạo nhiều mã vạch với cùng một cài đặt. Việc tái sử dụng đối tượng tránh việc cấp phát lại các tài nguyên nội bộ.  
* **Đặt `Resolution`** trên `ImageOptions` nếu bạn cần DPI cụ thể cho việc in:

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Xác thực đầu ra** bằng cách lập trình với `BarCodeReader` để đảm bảo PNG đã tạo có thể giải mã trước khi phát hành cho người dùng.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch PDF417** trong C# và **tạo tệp PNG mã vạch** với khả năng kiểm soát đầy đủ kích thước, cột và chế độ gọn. Ví dụ đầy đủ minh họa cách tiếp cận tiêu chuẩn, giải thích lý do mỗi cài đặt quan trọng, và đề cập đến các biến thể như sửa lỗi, định dạng thay thế, và dữ liệu nhị phân. Hãy sử dụng các mẹo trên để điều chỉnh giải pháp phù hợp với quy trình làm việc của bạn, dù bạn đang xây dựng hệ thống bán vé, công cụ tạo nhãn logistics, hay bộ mã hoá tài liệu bảo mật.

---

**Bước tiếp theo**

* Khám phá các ký hiệu 2D khác (DataMatrix, QR) bằng cách sử dụng cùng lớp `BarcodeGenerator`.  
* Tích hợp việc tạo mã vạch vào API ASP.NET Core để cung cấp PNG theo yêu cầu.  
* Kết hợp ảnh mã vạch với các thư viện tạo PDF để nhúng trực tiếp vào báo cáo.

Chúc lập trình vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?

Các tutorial sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có ví dụ mã hoàn chỉnh, kèm giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch pdf417 trong C# – hướng dẫn từng bước](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Cách tạo mã vạch micro pdf417 trong C# – hướng dẫn từng bước](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [Cách tạo mã vạch PDF417 trong C# với chế độ gọn](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}