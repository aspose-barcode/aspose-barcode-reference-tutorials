---
category: general
date: 2026-10-12
description: Học cách tạo một ví dụ mã vạch Aspose bằng C# để tạo mã MacroPdf417 với
  đầy đủ siêu dữ liệu và đọc lại nó bằng BarCodeReader.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: vi
lastmod: 2026-10-12
og_description: Ví dụ mã vạch Aspose bằng C# cho thấy cách tạo mã MacroPdf417 có siêu
  dữ liệu nhúng và đọc lại bằng BarCodeReader.
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: Tạo ví dụ mã vạch Aspose với MacroPdf417 bằng C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: Cách tạo ví dụ mã vạch Aspose với MacroPdf417 trong C#
url: /vi/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách xây dựng ví dụ Aspose barcode với MacroPdf417 trong C#

Nếu bạn cần một **aspose barcode example** tạo mã vạch MacroPdf417 và đọc siêu dữ liệu được nhúng, hướng dẫn này sẽ chỉ cho bạn quy trình hoàn chỉnh. Bạn sẽ thấy cách cấu hình trình tạo, nhúng thông tin ở mức tệp, lưu ảnh và sau đó giải mã cùng dữ liệu bằng `BarCodeReader`.

Bài hướng dẫn bao gồm mọi thứ bạn cần biết để **C# barcode generation** với Aspose.BarCode, bao gồm các lỗi thường gặp và mẹo xử lý ID tệp lớn hoặc dấu thời gian tùy chỉnh.

## Những gì bạn cần

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc phiên bản mới hơn (mã hoạt động với .NET Core và .NET Framework)
* Visual Studio 2022 hoặc bất kỳ IDE nào hỗ trợ C#
* Giấy phép Aspose.BarCode đang hoạt động (bản dùng thử miễn phí đủ cho việc phát triển)
* Gói NuGet `Aspose.BarCode` đã được cài đặt trong dự án của bạn

Những yêu cầu này đảm bảo ví dụ chạy mà không cần cấu hình thêm.

## Bước 1: Thiết lập dự án ví dụ Aspose barcode

Tạo một ứng dụng console mới và thêm thư viện Aspose.BarCode:

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

Gói `Aspose.BarCode` cung cấp `BarcodeGenerator`, `BarCodeReader` và tất cả các kiểu cần thiết cho việc xử lý MacroPdf417.

### Tại sao bước này quan trọng
Việc thêm gói NuGet sẽ giải quyết các enum `EncodeTypes`, `DecodeType` và `BarCodeImageFormat` được sử dụng sau này. Nếu không có gói, trình biên dịch sẽ không nhận ra các ký hiệu này và ví dụ sẽ thất bại khi biên dịch.

## Bước 2: Tạo trình tạo mã vạch MacroPdf417

Mở **Program.cs** và thay thế mã mẫu bằng khối sau. Khối này tạo một `BarcodeGenerator` được cấu hình cho ký hiệu MacroPdf417 và thiết lập các tham số hiển thị cơ bản.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### Giải thích các thuộc tính quan trọng

| Property | Purpose | Typical range / notes |
|----------|---------|-----------------------|
| `MacroPdf417FileID` | Định danh duy nhất cho toàn bộ tệp | Phải ≤ 2³¹‑1 |
| `MacroPdf417SegmentID` | Chỉ mục của đoạn hiện tại | Bắt đầu từ 0 |
| `MacroPdf417SegmentsCount` | Tổng số đoạn trong tệp | Phải ≥ SegmentID |
| `MacroPdf417FileName` | Tên tệp dễ đọc cho con người | Tối đa 255 ký tự |
| `MacroPdf417Checksum` | Kiểm tra tổng CCITT‑16 của tệp gốc | Tính bằng công cụ bên ngoài nếu cần |
| `MacroPdf417FileSize` | Kích thước tệp gốc tính bằng byte | Hữu ích cho việc xác thực |
| `MacroPdf417TimeStamp` | Ngày/giờ tạo tệp | Dùng UTC để đồng nhất |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Thông tin định tuyến tùy chọn | Bất kỳ chuỗi nào lên tới 255 ký tự |
| `MacroPdf417Terminator` | Đánh dấu đoạn cuối cùng | Dùng `Set` cho đoạn cuối |

Các trường này tạo nên **barcode metadata** mà trình đọc có thể trích xuất sau này.

## Bước 3: Giải mã mã vạch và hiển thị siêu dữ liệu

Sau khi lưu ảnh, chương trình tiếp tục bằng cách mở tệp với `BarCodeReader`. Thêm đoạn mã sau vào phương thức `Main`, sau khối `using` trước đó:

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### Tại sao việc đọc lại lại quan trọng
`BarCodeReader` xác thực rằng siêu dữ liệu bạn đã nhúng được mã hoá đúng. Nếu bất kỳ thuộc tính nào bị thiếu hoặc nằm ngoài phạm vi, trình đọc sẽ trả về `null` cho trường đó, cho phép bạn xử lý lỗi một cách mềm dẻo.

## Bước 4: Chạy và kiểm tra kết quả

Thực thi chương trình:

```bash
dotnet run
```

Bạn sẽ thấy đầu ra console tương tự như:

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

Nếu các giá trị khớp với những gì bạn đã đặt ở Bước 2, **aspose barcode example** hoạt động như mong đợi.

## Các trường hợp đặc biệt và mẹo thực hành tốt nhất

| Situation | What to watch for | Recommended handling |
|-----------|-------------------|----------------------|
| **FileID exceeds 32‑bit range** | Aspose ném `ArgumentOutOfRangeException`. | Giữ ID ≤ 2 147 483 647 hoặc chia tệp thành nhiều khối MacroPdf417. |
| **Timestamp in local time** | Trình đọc ở múi giờ khác có thể hiểu sai giá trị. | Lưu dấu thời gian ở UTC (`DateTime.UtcNow`) và chuyển đổi khi hiển thị nếu cần. |
| **Large file size** | `MacroPdf417FileSize` là `int`; giá trị > 2 GB sẽ tràn. | Sử dụng trường tùy chỉnh hoặc chia tệp thành các đoạn nhỏ hơn. |
| **Missing segment** | Nếu `SegmentID` không tuần tự, việc tái tạo sẽ thất bại. | Xác thực thứ tự đoạn trước khi mã hoá hoặc sử dụng cài đặt sửa lỗi. |
| **Unsupported image format** | Lưu dưới dạng BMP có thể làm tăng kích thước đáng kể. | PNG là lựa chọn mặc định tốt; JPEG có thể dùng nếu chấp nhận nén mất dữ liệu. |

**Mẹo chuyên nghiệp:** Khi bạn tạo nhiều mã vạch trong một lô, hãy tái sử dụng một thể hiện `BarcodeGenerator` duy nhất và chỉ thay đổi `EncodeTypes` và văn bản nguồn. Điều này giảm việc cấp phát bộ nhớ và tăng tốc xử lý.

## Các chủ đề liên quan bạn có thể khám phá tiếp

* **Các ký hiệu macro khác** – Aspose cũng hỗ trợ MacroPdf417 với các mức sửa lỗi.
* **Nhúng mã vạch vào PDF** – Kết hợp `Aspose.PDF` với trình tạo mã vạch để tạo tài liệu có thể in.
* **Tích hợp ASP.NET Core** – Phục vụ các mã vạch được tạo trực tiếp từ một API web.
* **Quét qua thiết bị di động** – Sử dụng SDK `Aspose.BarCode.Cloud` để giải mã đa nền tảng.

Những chủ đề tiếp theo này mở rộng tự nhiên **aspose barcode example** và nâng cao chuyên môn của bạn trong **C# barcode generation**.

## Kết luận

Bạn đã có một **aspose barcode example** hoàn chỉnh, tạo mã vạch MacroPdf417, nhúng siêu dữ liệu phong phú, lưu ảnh và đọc lại dữ liệu bằng `BarCodeReader`. Bằng cách làm theo các bước trên, bạn có thể điều chỉnh mã cho các ID tệp, dấu thời gian khác nhau, hoặc thậm chí các loại mã vạch khác mà Aspose hỗ trợ.

Hãy thoải mái thử nghiệm thêm các trường siêu dữ liệu, thay đổi định dạng ảnh, hoặc tích hợp trình tạo vào ứng dụng lớn hơn. Chúc bạn lập trình vui vẻ!

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}