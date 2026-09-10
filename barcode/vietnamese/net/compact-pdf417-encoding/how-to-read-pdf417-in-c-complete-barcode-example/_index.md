---
category: general
date: 2026-07-27
description: Cách đọc mã vạch PDF417 trong C# nhanh chóng. Học cách đọc nhiều mã vạch,
  giải mã hình ảnh và lấy siêu dữ liệu Macro PDF417 trong một ví dụ mã vạch C# đầy
  đủ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: vi
lastmod: 2026-07-27
og_description: Cách đọc mã vạch PDF417 trong C# với hướng dẫn từng bước này. Giải
  mã hình ảnh, xử lý nhiều mã vạch và trích xuất siêu dữ liệu Macro PDF417 trong một
  ví dụ sẵn sàng chạy.
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: Cách đọc PDF417 trong C# – Ví dụ đầy đủ về mã vạch
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: Cách đọc PDF417 trong C# – Ví dụ hoàn chỉnh về mã vạch
url: /vi/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đọc PDF417 trong C# – Ví dụ Đầy Đủ về Mã Vạch

Bạn đã bao giờ tự hỏi **cách đọc mã vạch PDF417** trong một ứng dụng C# mà không phải rối bời? Bạn không phải là người duy nhất. Dù bạn đang xây dựng một máy quét logistics, một bộ kiểm tra vé, hay chỉ cần lấy dữ liệu từ một CMND được mã hoá PDF417, quá trình này có thể cảm thấy hơi bí ẩn lúc đầu.  

Trong tutorial này, chúng ta sẽ đi qua một **c# barcode example** đọc ảnh PDF417, xử lý **read multiple barcodes** nếu có, và trích xuất tất cả các siêu dữ liệu Macro PDF417 hữu ích mà bạn có thể cần.

## Những gì bạn sẽ xây dựng

Khi hoàn thành hướng dẫn này, bạn sẽ có một chương trình console nhỏ có khả năng:

1. Tải ảnh mã vạch từ đĩa.  
2. Giải mã **PDF417** (bao gồm Macro PDF417).  
3. In ra thông tin cơ bản như loại mã và văn bản.  
4. Xuất toàn bộ các trường Macro PDF417 (file ID, segment ID, checksum, v.v.).  

Không cần dịch vụ bên ngoài, chỉ một gói NuGet và vài dòng C#.

## Điều kiện tiên quyết – Những gì bạn cần trước khi bắt đầu

- **.NET 6.0** trở lên (mã cũng chạy trên .NET Framework 4.6+).  
- Phiên bản mới của thư viện **Aspose.BarCode for .NET** – cài đặt qua NuGet (`Install-Package Aspose.BarCode`).  
- Một file ảnh chứa mã vạch PDF417 (bản demo sử dụng `ExtPDF417Meta.png`).  
- Kiến thức cơ bản về ứng dụng console C# (nếu bạn đã viết “Hello World”, bạn đã sẵn sàng).

> **Mẹo chuyên nghiệp:** Nếu bạn chưa có mẫu PDF417, hãy tạo một trên trang demo của Aspose hoặc dùng ứng dụng điện thoại thông minh có khả năng tạo thẻ PDF417.

## Bước 1: Thiết lập dự án và cài đặt thư viện

Đầu tiên, tạo một dự án console mới:

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

Điều này sẽ kéo các phụ thuộc **c# barcode example** mà chúng ta cần. Mở `Program.cs` và thay thế mã mặc định bằng khung skeleton dưới đây:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## Bước 2: Khởi tạo Barcode Reader cho PDF417

Trái tim của giải pháp là lớp `BarCodeReader`. Chúng ta chỉ định file cần quét và loại mã vạch quan tâm — trong trường hợp này là `DecodeType.Pdf417` hoặc biến thể macro `DecodeType.MacroPdf417`. Sử dụng loại macro giúp chúng ta nắm bắt các trường mở rộng.

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

Tại sao lại dùng `MacroPdf417` thay vì `Pdf417` thông thường? Macro PDF417 chứa thêm siêu dữ liệu (file ID, số lượng segment, timestamp, v.v.) mà nhiều ứng dụng thực tế dựa vào — ví dụ như manifest vận chuyển được chia thành nhiều trang.

## Bước 3: Đọc tất cả các mã vạch có trong ảnh

Một ảnh duy nhất có thể chứa **read multiple barcodes** — có thể là một QR code bên cạnh PDF417. Phương thức `ReadBarCodes()` trả về một `IEnumerable<BarCodeResult>` mà chúng ta có thể lặp qua.

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

Nếu ảnh chỉ có một PDF417, vòng lặp vẫn chạy một lần, giữ cho mã linh hoạt cho các kịch bản tương lai khi bạn cần **read multiple barcodes** từ cùng một lần quét.

## Bước 4: Hiển thị thông tin cơ bản của mã vạch

Trước khi đi sâu vào các trường macro, việc hiển thị loại mã và văn bản đã giải mã là hữu ích. Điều này giúp bạn xác nhận rằng trình đọc thực sự nhận diện được PDF417 chứ không phải một symbology khác.

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

Thuộc tính `CodeTypeName` sẽ trả về *MacroPdf417* (hoặc *Pdf417* nếu cờ macro không được đặt), trong khi `CodeText` chứa dữ liệu thô được mã hoá trong mã vạch.

## Bước 5: Trích xuất siêu dữ liệu Macro PDF417

Thuộc tính `Extended` cung cấp cái nhìn sâu vào cấu trúc đặc thù của PDF417. Mỗi trường chúng ta in ra dưới đây tương ứng trực tiếp với thông số kỹ thuật macro của PDF417.

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

Mỗi dòng lấy một phần khác nhau của payload macro:

- **FileID** – định danh duy nhất cho toàn bộ tập tài liệu.  
- **SegmentID** – phần nào của file đa segment bạn đang xem.  
- **SegmentsCount** – tổng số segment dự kiến.  
- **FileName, Checksum, FileSize** – hữu ích để xác thực tính toàn vẹn của file đã truyền.  
- **TimeStamp, Addressee, Sender** – các trường tùy chọn mà nhiều hệ thống logistics nhúng vào.  

Nếu bất kỳ trường nào này thiếu trong mã vạch nguồn, thư viện sẽ trả về `null` hoặc `0`, bạn có thể xử lý tùy ý.

## Bước 6: Chạy ví dụ hoàn chỉnh

Kết hợp tất cả lại, đây là chương trình đầy đủ, sẵn sàng chạy:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Kết quả mong đợi

Khi bạn chạy chương trình với file `ExtPDF417Meta.png` hợp lệ, bạn sẽ thấy đầu ra tương tự như:

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

Nếu ảnh chứa hơn một mã vạch,


## Bạn nên học gì tiếp theo?


Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}