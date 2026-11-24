---
category: general
date: 2026-11-23
description: Tìm hiểu cách tạo hình ảnh mã vạch bằng Aspose.BarCode cho .NET với siêu
  dữ liệu MacroPdf417 trong C#. Thực hiện theo hướng dẫn chi tiết từng bước.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: vi
lastmod: 2026-11-23
og_description: Cách tạo hình ảnh mã vạch bằng Aspose.BarCode cho .NET. Hướng dẫn
  này trình bày cấu hình siêu dữ liệu MacroPdf417 và việc tạo mã vạch bằng C#.
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: Cách tạo hình ảnh mã vạch với MacroPdf417 trong C#
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: Cách tạo ảnh mã vạch bằng MacroPdf417 trong C#
url: /vi/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo hình ảnh mã vạch với MacroPdf417 trong C#

Nếu bạn cần **tạo hình ảnh mã vạch** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chính xác bằng **Aspose.BarCode for .NET**. Chúng tôi sẽ hướng dẫn tạo một **mã vạch MacroPdf417**, cấu hình siêu dữ liệu của nó, và lưu kết quả dưới dạng tệp PNG.

Hướng dẫn này bao gồm mọi thứ từ việc cài đặt thư viện đến viết một chương trình console hoàn chỉnh, có thể chạy được. Khi kết thúc, bạn sẽ có một mẫu mã sẵn sàng sử dụng để tạo ra hình ảnh mã vạch chất lượng cao, và bạn sẽ hiểu cách **đặt siêu dữ liệu mã vạch**, chọn **định dạng hình ảnh mã vạch**, và khắc phục các vấn đề thường gặp. Không yêu cầu kinh nghiệm trước với Aspose—chỉ cần kiến thức cơ bản về C#.

## Cài đặt Aspose.BarCode cho .NET

Trước khi bạn có thể **tạo hình ảnh mã vạch**, bạn cần gói NuGet Aspose.BarCode.

1. Mở terminal hoặc Package Manager Console trong Visual Studio.  
2. Chạy lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

Gói này sẽ thêm namespace `Aspose.BarCode.Generation`, chứa lớp `BarcodeGenerator` được sử dụng cho **việc tạo mã vạch C#**.

> **Mẹo chuyên nghiệp:** Sử dụng phiên bản ổn định mới nhất (tính đến tháng 11 2026, phiên bản hiện tại là 24.11) để có các tính năng và bản sửa lỗi mới nhất.

## Tạo đối tượng BarcodeGenerator

Bước mã đầu tiên tạo một `BarcodeGenerator` được cấu hình cho loại **mã vạch MacroPdf417** và cung cấp chuỗi dữ liệu bạn muốn mã hoá.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

Khối `using` đảm bảo rằng trình tạo được giải phóng đúng cách, giải phóng bất kỳ tài nguyên không quản lý nào.

## Cấu hình giao diện cơ bản

Một mã vạch dễ đọc bắt đầu với kích thước hợp lý. Ở đây chúng ta đặt độ rộng pixel của mỗi mô-đun (`XDimension`) và số cột cho ma trận PDF417.

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*Vì sao lại dùng các giá trị này?*  
- **XDimension** kiểm soát độ dày của mỗi thanh; 2 pixel hoạt động tốt cho hiển thị trên màn hình và hầu hết các máy in.  
- **Columns** ảnh hưởng đến độ rộng tổng thể; số cột ít sẽ giữ mã vạch gọn gàng trong khi vẫn duy trì khả năng sửa lỗi.

## Đặt siêu dữ liệu mã vạch (đặc thù MacroPdf417)

MacroPdf417 cho phép bạn nhúng thông tin cấp file trực tiếp vào mã vạch. Đây là nơi bạn **đặt siêu dữ liệu mã vạch** như ID file, ID đoạn, và dấu thời gian.

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Ý nghĩa của từng thuộc tính

| Property | Purpose |
|----------|---------|
| **MacroPdf417FileID** | Định danh duy nhất cho file logic mà mã vạch thuộc về. |
| **MacroPdf417SegmentID** | Chỉ mục của đoạn hiện tại (bắt đầu từ 0). |
| **MacroPdf417SegmentsCount** | Tổng số đoạn tạo nên toàn bộ file. |
| **MacroPdf417FileName** | Tên file nguồn có thể đọc được bởi con người. |
| **MacroPdf417Checksum** | Kiểm tra tổng CCITT‑16 tùy chọn để xác minh tính toàn vẹn dữ liệu. |
| **MacroPdf417FileSize** | Kích thước dự kiến của file gốc tính bằng byte. |
| **MacroPdf417TimeStamp** | Ngày và giờ tạo mã vạch – hữu ích cho việc theo dõi phiên bản. |
| **MacroPdf417Addressee / Sender** | Các chuỗi tùy chỉnh có thể chứa thông tin định tuyến. |
| **MacroPdf417Terminator** | Chỉ ra liệu đoạn này có phải là đoạn cuối cùng (`Set`) hay không (`Unset`). |

> **Trường hợp đặc biệt:** Nếu bạn dự định chia một tài liệu lớn thành nhiều đoạn, hãy giữ `SegmentsCount` nhất quán trên tất cả các mã vạch được tạo. Số lượng không khớp sẽ gây lỗi giải mã.

## Chọn định dạng hình ảnh mã vạch và lưu

Aspose hỗ trợ nhiều **định dạng hình ảnh mã vạch** (PNG, JPEG, BMP, TIFF, v.v.). PNG không mất dữ liệu và hoạt động tốt cho hầu hết các kịch bản web và in ấn.

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

Thay thế `YOUR_DIRECTORY` bằng thư mục tuyệt đối hoặc tương đối mà ứng dụng có quyền ghi.

Khi chương trình chạy, bạn sẽ thấy một thông báo console xác nhận vị trí tệp. Mở tệp PNG bằng bất kỳ trình xem ảnh nào—bạn sẽ thấy một **mã vạch MacroPdf417** sắc nét, mã hoá văn bản đã cung cấp và siêu dữ liệu bạn đã định nghĩa.

### Kết quả mong đợi

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

Kích thước tệp ảnh sẽ khoảng 30‑40 KB, tùy thuộc vào `XDimension` và số cột đã chọn.

## Kiểm tra mã vạch và khắc phục sự cố

1. **Kiểm tra trực quan** – Mã vạch nên hiển thị một loạt các cột xếp chồng với vùng yên tĩnh (lề trắng) xung quanh.  
2. **Kiểm tra giải mã** – Sử dụng ứng dụng quét mã vạch hoặc lớp `BarCodeReader` của Aspose.BarCode để đọc lại hình ảnh và xác nhận rằng tất cả các trường siêu dữ liệu đã được nhúng đúng.



## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh, hoạt động với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo hình ảnh mã vạch PDF417 với Aspose.BarCode trong C# – hướng dẫn chi tiết](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [Cách tạo mã vạch với văn bản tùy chỉnh bằng Aspose.BarCode cho .NET](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [Cách đọc mã vạch từ ảnh bằng C# với Aspose.BarCode – hướng dẫn chi tiết](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}