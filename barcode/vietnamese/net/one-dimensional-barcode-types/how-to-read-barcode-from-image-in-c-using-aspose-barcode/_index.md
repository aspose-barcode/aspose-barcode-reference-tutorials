---
category: general
date: 2026-10-18
description: Học cách đọc mã vạch từ hình ảnh trong C# với Aspose.BarCode, bao gồm
  việc trích xuất siêu dữ liệu Macro PDF417 và mã mẫu đầy đủ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: vi
lastmod: 2026-10-18
og_description: Cách đọc mã vạch từ hình ảnh bằng C# Aspose.BarCode. Thực hiện theo
  hướng dẫn từng bước này để trích xuất siêu dữ liệu Macro PDF417 và xử lý các tình
  huống phổ biến.
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: Cách đọc mã vạch từ hình ảnh trong C# – hướng dẫn đầy đủ Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách đọc mã vạch từ hình ảnh trong C# bằng Aspose.BarCode
url: /vi/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đọc mã vạch từ hình ảnh trong C# sử dụng Aspose.BarCode

Nếu bạn cần **cách đọc mã vạch từ hình ảnh** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ ra các bước cụ thể với Aspose.BarCode. Dù bạn đang xử lý tài liệu quét, biên lai, hay thẻ tồn kho, bạn sẽ thấy cách đọc mã vạch, lấy siêu dữ liệu Macro PDF417, và xử lý các trường hợp đặc biệt thường gặp.

Đọc mã vạch từ một hình ảnh là một nhiệm vụ thường xuyên, nhưng việc trích xuất các trường Macro PDF417 mở rộng sẽ thêm một lớp phức tạp. Bài hướng dẫn này bao phủ toàn bộ quy trình làm việc, từ thiết lập dự án đến một ví dụ có thể chạy được đầy đủ, để bạn có thể sao chép‑dán mã và thấy kết quả ngay lập tức.

## Những gì bạn sẽ học

- Cách thiết lập Aspose.BarCode cho các dự án C#.  
- Cách khởi tạo **trình đọc mã vạch C#** cho một hình ảnh Macro PDF417 một cách đúng đắn.  
- Cách lặp qua từng mã vạch được phát hiện và xuất thông tin cơ bản.  
- Cách truy cập **siêu dữ liệu Macro PDF417** như file ID, segment ID và checksum.  
- Mẹo xử lý trường hợp thiếu siêu dữ liệu, hình ảnh lớn, và các lỗi giải mã thường gặp.  

**Yêu cầu trước**

- .NET 6.0 (hoặc mới hơn) đã được cài đặt.  
- Kiến thức cơ bản về C# và Visual Studio (bất kỳ IDE nào cũng được).  
- Một tệp hình ảnh chứa mã vạch Macro PDF417 (ví dụ: `ExtPDF417Meta.png`).  

## Bước 1: Cài đặt Aspose.BarCode

Mở terminal trong thư mục dự án của bạn và chạy:

```bash
dotnet add package Aspose.BarCode
```

Gói này bao gồm lớp **BarCodeReader**, thực hiện chức năng **trình đọc mã vạch C#** cần thiết cho bài hướng dẫn này.

## Bước 2: Thiết lập môi trường phát triển

Tạo một ứng dụng console mới nếu bạn chưa có:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

Thêm các chỉ thị `using` vào đầu file `Program.cs`:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

Các không gian tên này cung cấp lớp **BarCodeReader** và enumeration `DecodeType` cần thiết cho việc giải mã Macro PDF417.

## Bước 3: Khởi tạo BarCodeReader cho Macro PDF417

Cốt lõi của **cách đọc mã vạch từ hình ảnh** là tạo một thể hiện `BarCodeReader` nhắm vào `DecodeType` cụ thể. Đối với Macro PDF417 bạn phải truyền `DecodeType.MacroPdf417`:

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**Tại sao lại quan trọng:**  
Việc chọn `DecodeType.MacroPdf417` thông báo cho thư viện tìm kiếm định dạng Macro PDF417 mở rộng, chứa các trường bổ sung ngoài dữ liệu mã vạch cơ bản. Nếu bạn dùng `DecodeType.Pdf417` chung, những trường bổ sung đó sẽ bị bỏ qua.

## Bước 4: Lặp qua các mã vạch được phát hiện

Một hình ảnh duy nhất có thể chứa nhiều mã vạch. Phương thức `ReadBarCodes()` trả về một tập hợp các đối tượng `BarCodeResult`. Duyệt qua chúng để xuất thông tin cơ bản của mỗi mã vạch:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

Thuộc tính `CodeTypeName` cho bạn biết loại symbology chính xác (ví dụ: “MacroPdf417”), trong khi `CodeText` chứa chuỗi đã giải mã.

## Bước 5: Trích xuất và hiển thị siêu dữ liệu Macro PDF417

Khi mã vạch là Macro PDF417, thuộc tính `Extended.Pdf417` cung cấp một tập hợp phong phú các trường siêu dữ liệu. Truy cập chúng trực tiếp như dưới đây:

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Các trường này cung cấp mọi thứ bạn cần để tái tạo lại tệp đa đoạn gốc, xác minh tính toàn vẹn, và liên kết mã vạch với một tài liệu hoặc người gửi cụ thể.

### Đầu ra console dự kiến

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

Nếu hình ảnh không chứa mã vạch Macro PDF417, đối tượng `Extended.Pdf417` sẽ là `null`. Hãy kiểm tra để tránh `NullReferenceException`:

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## Bước 6: Xử lý các lỗi và trường hợp đặc biệt thường gặp

### Hình ảnh lớn

Đọc các hình ảnh rất lớn có thể tiêu tốn bộ nhớ đáng kể. Sử dụng overload của `BarcodeReader` chấp nhận `ReaderParameters` để giới hạn kích thước tối đa của hình ảnh:

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### Thiếu hoặc siêu dữ liệu bị hỏng

Nếu bất kỳ trường Macro nào bị thiếu, thuộc tính tương ứng sẽ trả về `null` hoặc `0`. Ghi lại các trường hợp này và quyết định xem có nên coi mã vạch là không đầy đủ hay không.

### Nhiều loại mã vạch trong một hình ảnh

Nếu một hình ảnh có thể chứa các định dạng mã vạch khác, bạn có thể truyền một mảng các giá trị `DecodeType`:

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

Cách tiếp cận này giữ cho logic **cách đọc mã vạch từ hình ảnh** linh hoạt mà không làm giảm hiệu năng.

## Bước 7: Mã nguồn đầy đủ

Dưới đây là chương trình hoàn chỉnh, sẵn sàng chạy. Thay `YOUR_DIRECTORY/ExtPDF417Meta.png` bằng đường dẫn tới hình ảnh của bạn.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

Chạy chương trình bằng:

```bash
dotnet run
```

Bạn sẽ thấy loại mã vạch, văn bản đã giải mã, và tất cả các trường Macro PDF417 khả dụng được in ra console.

## Kết luận

Trong bài hướng dẫn này bạn đã học **cách đọc mã vạch từ hình ảnh** bằng Aspose.BarCode cho C#. Hướng dẫn đã bao phủ việc thiết lập **trình đọc mã vạch C#**,

## Bạn nên học gì tiếp theo?

Các bài hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to read PDF417 barcode c# – complete step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}