---
category: general
date: 2026-10-15
description: Cách đọc nhanh hình ảnh mã vạch trong C# bằng BarCodeReader. Học cách
  đọc nhiều mã vạch và xem ví dụ trình đọc mã vạch C# hoạt động với Macro‑PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: vi
lastmod: 2026-10-15
og_description: Cách đọc mã vạch trong C# bằng BarCodeReader. Hướng dẫn này trình
  bày một ví dụ đầy đủ về trình đọc mã vạch C# có khả năng xử lý nhiều mã vạch và
  trích xuất siêu dữ liệu Macro‑PDF417.
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: Cách đọc mã vạch trong C# – ví dụ từng bước
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách đọc hình ảnh mã vạch trong C# – hướng dẫn đầy đủ với ví dụ
url: /vi/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đọc ảnh mã vạch trong C# – hướng dẫn ví dụ đầy đủ

Nếu bạn cần **cách đọc mã vạch** dữ liệu từ một hình ảnh trong ứng dụng .NET, hướng dẫn này cung cấp cho bạn một giải pháp sẵn sàng chạy. Bạn sẽ thấy một **ví dụ đọc mã vạch c#** hoàn chỉnh hoạt động với các ký hiệu Macro‑PDF417 và có thể **đọc nhiều mã vạch** từ một bức ảnh duy nhất.

Đọc mã vạch là một yêu cầu phổ biến cho các hệ thống tồn kho, xác thực vé và xử lý tài liệu. Khi kết thúc tutorial này, bạn sẽ có thể:

* Khởi tạo `BarCodeReader` cho bất kỳ định dạng nào được hỗ trợ.  
* Trích xuất thông tin cơ bản như loại mã và văn bản đã giải mã.  
* Lấy siêu dữ liệu đặc thù của Macro‑PDF417 (ID tệp, đoạn, checksum, …).  
* Xử lý các hình ảnh chứa nhiều mã vạch mà không cần thêm mã.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt.  
* Môi trường phát triển (Visual Studio 2022, VS Code, hoặc Rider).  
* Gói NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – cung cấp lớp `BarCodeReader` được sử dụng trong ví dụ.  
* Một tệp hình ảnh chứa mã vạch Macro‑PDF417 (ví dụ, `MacroPdf417.png`).  

Bạn có thể cài đặt gói NuGet bằng lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

## Cách đọc mã vạch với BarCodeReader trong C#

Cốt lõi của giải pháp bao gồm bốn bước ngắn gọn. Mỗi bước được bao bọc trong một khối `using` để đảm bảo các tài nguyên không quản lý được giải phóng kịp thời.

### Bước 1: Khởi tạo `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**Tại sao điều này quan trọng:**  
`BarCodeReader` chấp nhận một đường dẫn tệp và một `DecodeType`. Việc chỉ định `DecodeType.MacroPdf417` báo cho thư viện chỉ tìm kiếm các ký hiệu Macro‑PDF417, giúp tăng tốc độ phát hiện và giảm các kết quả sai.

### Bước 2: Đọc tất cả các mã vạch có trong hình ảnh

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**Tại sao điều này quan trọng:**  
Phương thức `ReadBarCodes()` trả về một mảng có thể chứa một hoặc nhiều đối tượng `BarCodeResult`. Đây là lúc khả năng **đọc nhiều mã vạch** tỏa sáng – bạn không cần một vòng lặp riêng cho mỗi mã vạch có thể có.

### Bước 3: Hiển thị chi tiết mã vạch cơ bản

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**Tại sao điều này quan trọng:**  
`CodeTypeName` cho bạn biết ký hiệu nào đã được phát hiện (ví dụ, “MacroPDF417”), trong khi `CodeText` chứa dữ liệu đã giải mã. Hai trường này là những trường được sử dụng thường xuyên nhất trong logic downstream.

### Bước 4: Lấy và hiển thị siêu dữ liệu đặc thù của Macro‑PDF417

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**Tại sao điều này quan trọng:**  
Macro‑PDF417 mở rộng định dạng PDF417 thông thường bằng siêu dữ liệu ở mức tài liệu. Truy cập thuộc tính `Extended.Pdf417` cung cấp cho bạn mọi thứ cần thiết để tái tạo tệp gốc, xác thực tính toàn vẹn, hoặc chuyển dữ liệu đến người nhận phù hợp.

### Chương trình đầy đủ có thể chạy

Dưới đây là một ứng dụng console tự chứa, kết hợp cả bốn bước lại với nhau. Sao chép mã vào một tệp `.cs` mới, điều chỉnh `imagePath`, và chạy `dotnet run`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### Đầu ra console dự kiến

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

Nếu hình ảnh chứa nhiều hơn một ký hiệu Macro‑PDF417, chương trình sẽ in một khối riêng cho mỗi mã vạch, minh họa khả năng **đọc nhiều mã vạch** mà không cần thêm bất kỳ mã nào.

## Xử lý các trường hợp góc cạnh phổ biến

| Tình huống | Cách thực hiện | Lý do |
|-----------|----------------|-------|
| **Tệp không tồn tại** | Bao quanh việc tạo `BarCodeReader` bằng một khối `try/catch (FileNotFoundException)` và hiển thị thông báo thân thiện. | Ngăn ứng dụng bị sập và thông báo cho người dùng về tài nguyên bị thiếu. |
| **Không phát hiện mã vạch** | Kiểm tra `results.Length == 0` (như trong chương trình đầy đủ) và xử lý một cách nhẹ nhàng. | Cung cấp phản hồi rõ ràng khi hình ảnh không chứa bất kỳ ký hiệu nào được hỗ trợ. |
| **Loại mã vạch khác** | Thay đổi `DecodeType.MacroPdf417` thành `DecodeType.AllSupportedTypes` hoặc một giá trị enum cụ thể khác. | Cho phép cùng một mã nguồn làm việc với QR, Code128, DataMatrix, v.v., đồng thời vẫn hỗ trợ **đọc nhiều mã vạch**. |
| **Hình ảnh lớn** | Đặt `reader.AutoSize = true` hoặc giảm kích thước hình ảnh trước khi đưa vào bộ đọc. | Cải thiện hiệu suất và giảm áp lực bộ nhớ trên CLR. |
| **Sử dụng an toàn đa luồng** | Tạo một thể hiện `BarCodeReader` riêng cho mỗi luồng; lớp này không an toàn đa luồng. | Tránh các điều kiện race trong các máy quét đa luồng hoặc dịch vụ web. |

## Mẹo chuyên nghiệp cho mã sản xuất

* **Dispose early:** Câu lệnh `using` đảm bảo các tài nguyên gốc (ví dụ, bộ đệm hình ảnh) được giải phóng kịp thời. Trong các dịch vụ chạy lâu, hãy giải phóng bộ đọc ngay khi bạn hoàn thành xử lý mỗi hình ảnh.  
* **Xử lý hàng loạt**

## Bạn Nên Học Gì Tiếp Theo?

Các tutorial sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoạt động đầy đủ với các giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}