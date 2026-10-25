---
category: general
date: 2026-10-24
description: Tìm hiểu cách đọc mã vạch PDF417 trong C# bằng Aspose.BarCode. Hướng
  dẫn này bao gồm việc đọc ảnh mã vạch, trích xuất các trường Macro PDF417 và xử lý
  các tình huống phổ biến.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: vi
lastmod: 2026-10-24
og_description: Cách đọc mã vạch PDF417 trong C# bằng Aspose.BarCode. Tham khảo hướng
  dẫn đầy đủ này để giải mã hình ảnh, lấy siêu dữ liệu Macro PDF417 và tránh các lỗi
  thường gặp.
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: Cách đọc mã vạch PDF417 trong C# với Aspose – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: Cách đọc mã vạch PDF417 trong C# với Aspose – hướng dẫn từng bước
url: /vi/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đọc mã vạch PDF417 trong C# với Aspose – hướng dẫn từng bước

Nếu bạn cần **cách đọc mã vạch PDF417** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách đọc mã vạch PDF417 trong C# bằng thư viện Aspose.BarCode. Dù bạn đang xử lý tài liệu quét, ảnh chụp từ thiết bị di động, hay các hình ảnh được nhập hàng loạt, đoạn mã dưới đây sẽ giải mã mã vạch và trích xuất mọi thuộc tính Macro PDF417 mà bạn có thể cần.

Đọc ảnh mã vạch trong C# có thể cảm thấy khó khăn, đặc biệt khi mã vạch chứa siêu dữ liệu mở rộng. Bài học này loại bỏ mọi suy đoán bằng cách cung cấp một ví dụ hoàn chỉnh, có thể chạy được, giải thích từng dòng và bao quát các trường hợp biên như thiếu segment macro hoặc ảnh bị hỏng. Khi hoàn thành, bạn sẽ có thể tích hợp việc giải mã PDF417 vào bất kỳ dự án C# nào một cách tự tin.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

* .NET 6.0 SDK hoặc phiên bản mới hơn được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ .NET)  
* Giấy phép hoặc bản dùng thử miễn phí của **Aspose.BarCode for .NET** – bạn có thể lấy khóa tạm thời từ trang web Aspose  
* Một tệp ảnh chứa mã vạch Macro PDF417 (ví dụ: `ExtPDF417Meta.png`)

> **Mẹo chuyên nghiệp:** Nếu bạn chỉ muốn thử nghiệm, Aspose cung cấp bản dùng thử 30 ngày với đầy đủ chức năng đọc mã vạch.

## Bước 1: Cài đặt gói NuGet Aspose.BarCode

Mở thư mục dự án của bạn trong terminal và chạy:

```bash
dotnet add package Aspose.BarCode
```

Gói này sẽ thêm không gian tên `Aspose.BarCode.ReadRecognition`, trong đó chứa lớp `BarCodeReader` dùng để giải mã ảnh.

## Bước 2: Tạo BarCodeReader cho ảnh PDF417

Constructor của `BarCodeReader` nhận hai đối số: đường dẫn tới tệp ảnh và `DecodeType` bạn muốn nhắm tới. Việc chỉ định `DecodeType.MacroPdf417` sẽ khiến Aspose tìm kiếm các ký hiệu Macro PDF417 và tự động điền các thuộc tính mở rộng.

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### Tại sao lại dùng `DecodeType.MacroPdf417`?

* **Macro PDF417** lưu trữ các trường bổ sung (ID tệp, số segment, dấu thời gian, v.v.) mà chuẩn PDF417 thông thường không có.  
* Thuộc tính `Extended` của `BarCodeResult` chỉ được điền khi bạn yêu cầu loại macro, giúp bạn tránh một bước phân tích riêng.

## Bước 3: Duyệt qua tất cả các mã vạch được phát hiện

Một ảnh duy nhất có thể chứa nhiều ký hiệu PDF417 (ví dụ, khi một tài liệu được chia thành nhiều trang). Phương thức `ReadBarCodes()` trả về một `IEnumerable<BarCodeResult>` mà bạn có thể lặp lại.

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

Nếu ảnh không chứa bất kỳ mã vạch nào, vòng lặp sẽ không thực thi và chương trình sẽ kết thúc một cách êm thấm. Hành vi này làm cho mã an toàn khi xử lý hàng loạt, nơi một số tệp có thể không có mã vạch.

## Bước 4: Xuất các thuộc tính mở rộng của Macro PDF417

Thuộc tính `Extended.Pdf417` nhóm lại tất cả các trường đặc thù của macro. Mỗi trường ánh xạ trực tiếp tới đặc tả PDF417, vì vậy bạn có thể lưu chúng vào cơ sở dữ liệu, ghi log, hoặc dùng để xác thực thêm.

```csharp
        // Macro PDF417 extended properties
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

### Ý nghĩa của từng thuộc tính

| Property | Description |
|----------|-------------|
| **MacroPdf417FileID** | Định danh duy nhất cho toàn bộ tài liệu đa‑segment. |
| **MacroPdf417SegmentID** | Chỉ mục của segment hiện tại (bắt đầu từ 0). |
| **MacroPdf417SegmentsCount** | Tổng số segment thuộc về tệp. |
| **MacroPdf417FileName** | Tên tệp tùy chọn được nhúng trong mã vạch. |
| **MacroPdf417Checksum** | Kiểm tra CRC‑16 cho khối dữ liệu macro. |
| **MacroPdf417FileSize** | Kích thước tệp gốc tính bằng byte. |
| **MacroPdf417TimeStamp** | Dấu thời gian khi macro barcode được tạo. |
| **MacroPdf417Addressee** | Người nhận dự định của tài liệu. |
| **MacroPdf417Sender** | Người gửi (nguồn gốc) của tài liệu. |
| **MacroPdf417Terminator** | Cờ kết thúc, chỉ ra sự kết thúc của chuỗi macro. |

Các trường này đặc biệt hữu ích khi bạn đang tái tạo một file PDF hoặc hình ảnh lớn đã được chia thành nhiều ký hiệu PDF417 để in trên phương tiện độ phân giải thấp.

## Bước 5: Xử lý các trường hợp biên phổ biến

### Thiếu các trường macro

Đôi khi một mã vạch PDF417 được tạo mà không có các trường macro tùy chọn. Truy cập một thuộc tính không tồn tại sẽ trả về `null` hoặc `0`. Hãy bảo vệ mã của bạn nếu dự định lưu các giá trị này:

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### Ảnh bị hỏng hoặc chất lượng thấp

Nếu ảnh bị mờ, bạn có thể cải thiện khả năng phát hiện bằng cách bật các tùy chọn chất lượng của `BarCodeReader`:

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

Các thiết lập này là tùy chọn nhưng có thể tăng đáng kể tỷ lệ thành công cho các tài liệu được quét.

### Nhiều định dạng mã vạch trong một ảnh

Nếu bạn nghi ngờ có các loại mã vạch khác xuất hiện, hãy dùng `DecodeType.AllSupported` và lọc kết quả:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## Ví dụ hoàn chỉnh có thể chạy

Sao chép chương trình dưới đây vào một dự án console mới (`dotnet new console`) và chạy. Thay đổi biến `imagePath` thành vị trí của ảnh Macro PDF417 của bạn.

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**Kết quả mong đợi** (giá trị sẽ khác tùy vào ảnh của bạn):

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

Nếu ảnh không chứa ký hiệu Macro PDF417, chương trình sẽ không in gì và thoát im lặng—rất phù hợp cho các công việc batch xử lý nhiều tệp.

## Câu hỏi thường gặp

**Q: Tôi có thể đọc PDF417 chuẩn (không phải macro) bằng cùng một đoạn mã không?**  
A: Có. Thay `DecodeType.MacroPdf417` bằng `DecodeType.Pdf417`. Thuộc tính `Extended` sẽ rỗng, nhưng `CodeText` và `CodeTypeName` vẫn khả dụng.

**Q: Aspose.BarCode có hỗ trợ đọc từ stream thay vì đường dẫn tệp không?**  
A: Hoàn toàn có. Sử dụng overload `new BarCodeReader(Stream, DecodeType)` và truyền vào một `FileStream` hoặc `MemoryStream`. Điều này hữu ích khi ảnh đến từ một API web.

**Q: Làm sao kiểm tra checksum?**  
A: Trường `MacroPdf417Checksum` chứa giá trị CRC‑16 thô. Bạn có thể tính lại checksum trên tệp đã tái tạo và so sánh để đảm bảo tính toàn vẹn dữ liệu.

## Các bước tiếp theo và chủ đề liên quan

* **Write PDF417 barcodes** – khám phá `BarCodeGenerator` để tạo macro barcode cho mục đích thử nghiệm.  
* **Combine multiple segments** – sau khi đọc hết các segment, sắp xếp chúng theo `MacroPdf417SegmentID` và nối `CodeText` để tái tạo payload gốc.  
* **Performance tuning** – trong các kịch bản xử lý tốc độ cao, tái sử dụng một thể hiện `BarCodeReader` duy nhất cho nhiều ảnh và

## Bạn Nên Học Gì Tiếp Theo?


Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong bài viết này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}