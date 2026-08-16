---
category: general
date: 2026-08-15
description: Đọc mã vạch từ hình ảnh trong C# bằng BarCodeReader. Tìm hiểu cách đọc
  nhiều mã vạch trong C#, đọc mã vạch PDF417, và xem một ví dụ đầy đủ về BarCodeReader
  trong C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: vi
lastmod: 2026-08-15
og_description: Đọc mã vạch từ hình ảnh trong C# với hướng dẫn từng bước. Khám phá
  cách đọc nhiều mã vạch trong C#, giải mã ký hiệu PDF417 và chạy một ví dụ hoàn chỉnh
  về BarCodeReader trong C#.
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: Đọc mã vạch từ hình ảnh trong C# – Hướng dẫn BarCodeReader
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: Đọc mã vạch từ hình ảnh trong C# – Hướng dẫn BarCodeReader
url: /vi/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc mã vạch từ hình ảnh trong C# – Hướng dẫn BarCodeReader

Nếu bạn cần **đọc mã vạch từ hình ảnh** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chính xác bằng lớp `BarCodeReader`. Bạn cũng sẽ thấy cách **đọc nhiều mã vạch C#**, giải mã ký hiệu PDF417, và có được một **ví dụ C# BarCodeReader** hoàn chỉnh mà bạn có thể sao chép vào dự án của mình.

Hướng dẫn bao gồm mọi bước—từ việc thêm gói NuGet cần thiết đến việc in các trường PDF417 mở rộng—để bạn có một chương trình console có thể chạy được. Không cần tài liệu bên ngoài; tất cả mã và giải thích đều được bao gồm.

## Những gì bạn cần

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc mới hơn (mã hoạt động với .NET Core và .NET Framework)
* Visual Studio 2022 hoặc bất kỳ trình soạn thảo nào hỗ trợ C#
* Gói NuGet `Aspose.BarCode` (hoặc thư viện tương đương cung cấp `BarCodeReader`)
* Một tệp hình ảnh chứa mã vạch Macro PDF417 (ví dụ: `ExtPDF417Meta.png`)

Có đầy đủ các điều kiện tiên quyết này sẽ đảm bảo mẫu biên dịch mà không cần cấu hình bổ sung.

## Đọc mã vạch từ hình ảnh bằng BarCodeReader

Bước đầu tiên là tạo một thể hiện `BarCodeReader` trỏ tới tệp hình ảnh và cho thư viện biết loại mã vạch cần tìm.

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Tại sao cách này hoạt động:**  
`BarCodeReader` mở hình ảnh, quét theo `DecodeType` đã chỉ định và trả về một tập hợp các đối tượng `BarCodeResult`. Mỗi kết quả chứa dữ liệu mã vạch chung (`CodeTypeName`, `CodeText`) và, đối với Macro PDF417, một đối tượng `Extended.Pdf417` hiển thị tất cả các trường bổ sung được định nghĩa trong tiêu chuẩn.

## Đọc nhiều mã vạch C# trong một hình ảnh duy nhất

Đôi khi một hình ảnh chứa hơn một mã vạch (ví dụ: QR code bên cạnh PDF417). Để xử lý trường hợp này, chỉ cần bỏ qua `DecodeType` cụ thể hoặc truyền `DecodeType.AllSupported` và lặp qua các kết quả.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**Tại sao bạn cần điều này:**  
Việc chỉ định `AllSupported` yêu cầu engine thử mọi định dạng mã vạch mà nó biết, đảm bảo bạn bắt được mọi ký hiệu trong hình ảnh. Đây là cách tiếp cận được khuyến nghị khi bạn không thể dự đoán trước loại mã vạch.

## Cách đọc mã vạch PDF417 bằng C#

Nếu bạn chỉ quan tâm đến định dạng PDF417 cổ điển (không phải macro), hãy đổi `DecodeType` thành `Pdf417`. Phần còn lại của mã vẫn giống hệt, chỉ khác là các trường mở rộng không có sẵn.

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**Tại sao điều này quan trọng:**  
PDF417 cổ điển không cung cấp các thuộc tính đặc thù của macro, vì vậy khối `Extended.Pdf417` là không cần thiết. Sử dụng `DecodeType` chính xác cũng giúp tăng tốc quét vì thư viện bỏ qua các thuật toán không hỗ trợ.

## Ví dụ đầy đủ C# BarCodeReader mà bạn có thể sao chép

Dưới đây là chương trình hoàn chỉnh kết hợp ba kịch bản thành một ứng dụng console dễ chạy. Thay thế `YOUR_DIRECTORY/ExtPDF417Meta.png` bằng đường dẫn thực tế tới hình ảnh của bạn.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### Kết quả mong đợi

Khi hình ảnh mẫu chứa mã vạch Macro PDF417, console sẽ in ra một nội dung tương tự như:

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

Nếu hình ảnh chỉ chứa PDF417 thông thường, phần “Macro PDF417” sẽ để trống, và phần “Classic PDF417” sẽ hiển thị văn bản đã giải mã.

## Kết luận

Bạn đã biết cách **đọc mã vạch từ hình ảnh** trong C# bằng `BarCodeReader`, cách **đọc nhiều mã vạch C#** trong một tệp duy nhất, và các bước chính xác để **đọc mã vạch PDF417**—cả phiên bản macro và cổ điển. Toàn bộ **ví dụ C# BarCodeReader** đã sẵn sàng để dán vào bất kỳ dự án .NET nào, và bạn có thể mở rộng nó để xử lý các định dạng khác hoặc tích hợp vào quy trình xử lý ảnh lớn hơn.

**Các bước tiếp theo**

* Khám phá các mẫu xử lý lỗi như `try / catch` quanh khối reader.  
* Thử nghiệm với đối tượng `ReaderParameters` để tinh chỉnh tốc độ và độ chính xác phát hiện.  
* Kết hợp việc đọc mã vạch với các thư viện tiền xử lý ảnh (

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoạt động đầy đủ với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách đọc mã DataMatrix với Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Đọc mã DataMatrix C# – Tạo chế độ DataMatrix (Tự động)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Đọc mã vạch từ hình ảnh – Thành thạo việc trích xuất vùng mã vạch trong Java với Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}