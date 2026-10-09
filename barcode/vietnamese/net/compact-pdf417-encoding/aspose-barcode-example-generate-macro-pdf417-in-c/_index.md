---
category: general
date: 2026-10-09
description: Tìm hiểu cách tạo mã vạch PDF417 trong C# bằng Aspose.BarCode – tạo Macro
  PDF417 với hỗ trợ metadata đầy đủ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: Tìm hiểu cách tạo mã vạch PDF417 trong C# bằng Aspose.BarCode – tạo
  Macro PDF417 với hỗ trợ metadata đầy đủ, bao gồm file ID, segment data, timestamp
  và các thông tin khác.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Cách tạo mã vạch PDF417 trong C# với Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: Cách tạo mã vạch PDF417 trong C# với Aspose.BarCode
url: /vi/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 trong C# với Aspose.BarCode

Nếu bạn cần **tạo mã vạch PDF417 C#** một cách nhanh chóng và đáng tin cậy, hướng dẫn này sẽ dẫn bạn qua toàn bộ quy trình sử dụng Aspose.BarCode. Bạn sẽ thấy mọi cài đặt cần thiết, từ kích thước cơ bản đến bộ đầy đủ các trường siêu dữ liệu Macro PDF417, và cuối cùng sẽ có một hình ảnh PNG sẵn sàng cho xử lý tiếp theo.

## Câu trả lời nhanh
- **Thư viện nào tạo mã vạch PDF417?** Aspose.BarCode cho .NET.  
- **Định dạng đầu ra của ví dụ là gì?** Một hình ảnh PNG không mất dữ liệu.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho mẫu; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Phiên bản .NET nào được hỗ trợ?** .NET 6.0 hoặc mới hơn.  
- **Tôi có thể thêm siêu dữ liệu vào mã vạch không?** Có – Macro PDF417 hỗ trợ ID tệp, số đoạn, dấu thời gian và nhiều hơn nữa.  

## Mã vạch PDF417 là gì?
Mã vạch PDF417 là một ký hiệu tuyến tính xếp chồng có thể mã hoá lên tới khoảng 1 KB dữ liệu mỗi ký hiệu và hỗ trợ siêu dữ liệu macro tùy chọn cho các tệp đa đoạn. Nó bao gồm nhiều hàng các mẫu tuyến tính xếp chồng, cho phép dung lượng dữ liệu cao trong khi vẫn có thể đọc được bằng các máy quét 2‑D tiêu chuẩn. Định dạng này cũng bao gồm các mức sửa lỗi để cải thiện độ tin cậy, và tính năng macro tùy chọn cho phép chia các tệp lớn thành nhiều mã vạch với siêu dữ liệu giúp tái tạo lại chúng.

## Tại sao nên sử dụng Aspose.BarCode cho PDF417?
Aspose.BarCode hỗ trợ **hơn 50 ký hiệu mã vạch** và có thể tạo mã vạch Macro PDF417 với tới **2 000 cột**, xử lý các tệp lớn hơn **10 MB** mà không cần tải toàn bộ dữ liệu vào bộ nhớ. Khả năng định lượng này đảm bảo các kịch bản doanh nghiệp có lưu lượng cao chạy mượt mà, và nó cung cấp nhiều tùy chọn tùy chỉnh.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

- .NET 6.0 (hoặc mới hơn) đã được cài đặt  
- Visual Studio 2022 hoặc bất kỳ IDE nào tương thích với C#  
- Giấy phép hợp lệ cho **Aspose.BarCode cho .NET** (bản dùng thử miễn phí hoạt động cho ví dụ này)  

Thêm gói NuGet Aspose.BarCode vào dự án của bạn:

```bash
dotnet add package Aspose.BarCode
```

## Cách tạo mã vạch PDF417 trong C#?

`BarcodeGenerator` là lớp chính để tạo hình ảnh mã vạch.  
`EncodeTypes.MacroPdf417` chọn ký hiệu Macro PDF417 cho việc tạo mã vạch.  
`Save` ghi mã vạch đã tạo vào một tệp hình ảnh.

Tải `BarcodeGenerator` với enum `EncodeTypes.MacroPdf417` và văn bản mục tiêu của bạn, sau đó gọi `Save` – đó là quy trình tạo hoàn chỉnh trong ba dòng. Trình tạo tự động xử lý Unicode, và câu lệnh `using` đảm bảo các tài nguyên không quản lý được giải phóng sau khi hình ảnh được lưu.

### Bước 1: tạo thể hiện BarcodeGenerator trong C#

Lớp `BarcodeGenerator` tạo và cấu hình hình ảnh mã vạch.  

Khởi tạo `BarcodeGenerator` với giá trị enum `EncodeTypes.MacroPdf417` và văn bản bạn muốn mã hoá. Văn bản có thể chứa ký tự Unicode, thư viện sẽ tự động xử lý.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Tại sao điều này quan trọng*: `EncodeTypes.MacroPdf417` thông báo cho engine tạo ra một ký hiệu Macro PDF417, hỗ trợ dữ liệu phân đoạn và siêu dữ liệu cấp tệp bổ sung. Câu lệnh `using` đảm bảo các tài nguyên không quản lý được giải phóng sau khi hình ảnh được lưu.

### Bước 2: định nghĩa giao diện cơ bản của mã vạch

`XDimension.Pixels` đặt kích thước của mỗi mô-đun mã vạch tính bằng pixel.

Một mã vạch Macro PDF417 bao gồm các mô-đun vuông. Kiểm soát kích thước mô-đun và số cột ảnh hưởng đến khả năng đọc và kích thước tệp.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Tại sao điều này quan trọng*: `XDimension.Pixels` xác định mật độ hình ảnh; giá trị 2 pixel hoạt động tốt cho hiển thị trên màn hình đồng thời giữ hình ảnh nhỏ gọn. Điều chỉnh số cột để phù hợp với ràng buộc bố cục của bạn—nhiều cột hơn tạo ra mã vạch rộng hơn, ngắn hơn.

### Bước 3: thiết lập siêu dữ liệu đặc thù cho Macro PDF417

`MacroPdf417FileID` xác định tệp mà tất cả các đoạn mã vạch thuộc về.

Macro PDF417 mở rộng định dạng PDF417 tiêu chuẩn với các trường cho phép tái tạo các tệp lớn từ nhiều đoạn mã vạch. Mỗi trường là tùy chọn, nhưng việc thiết lập chúng thể hiện đầy đủ khả năng của API.

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Tại sao điều này quan trọng*:  
- `MacroPdf417FileID` liên kết tất cả các đoạn thuộc cùng một tệp logic.  
- `MacroPdf417SegmentID` và `MacroPdf417SegmentsCount` cho phép bộ giải mã sắp xếp lại các đoạn một cách chính xác.  
- `MacroPdf417Checksum` cung cấp kiểm tra nhanh tính toàn vẹn mà không cần giải mã toàn bộ payload.  
- `MacroPdf417FileSize` và `MacroPdf417TimeStamp` cho phép hệ thống downstream xác nhận rằng tệp đã được tái tạo khớp với bản gốc.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` hữu ích trong các kịch bản logistics hoặc trao đổi tài liệu.  
- Đặt `MacroPdf417Terminator` thành `Set` đánh dấu mã vạch này là đoạn cuối cùng, giúp đơn giản hoá thuật toán tái tạo.

### Bước 4: lưu hình ảnh mã vạch đã tạo

`Save` ghi hình ảnh mã vạch vào đường dẫn tệp đã chỉ định.

Cuối cùng, ghi mã vạch vào tệp PNG. Bạn có thể chọn bất kỳ định dạng hỗ trợ nào (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Tại sao điều này quan trọng*: PNG giữ nguyên dữ liệu pixel không mất mát, đảm bảo máy quét đọc đúng mẫu mô-đun bạn đã cấu hình. Thay đổi định dạng có thể ảnh hưởng đến chất lượng hình ảnh và kích thước tệp.

#### Kết quả mong đợi

Chạy chương trình đầy đủ sẽ tạo ra một tệp có tên **ExtPDF417Meta.png**. Mở hình ảnh sẽ thấy một mã vạch Macro PDF417 hình chữ nhật với văn bản “Åspóse.Barcóde©” đã được mã hoá, và mật độ hình ảnh khớp với kích thước X 2‑pixel bạn đã đặt. Quét hình ảnh bằng trình đọc hỗ trợ PDF417 sẽ trả về tất cả các trường siêu dữ liệu được định nghĩa ở Bước 3.

## Ví dụ hoạt động đầy đủ

Sao chép mã dưới đây vào một dự án console mới (`dotnet new console`) và thay thế `YOUR_DIRECTORY` bằng đường dẫn tuyệt đối hoặc tương đối tồn tại trên máy của bạn.

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

Chạy chương trình (`dotnet run`). Sau khi thực thi, xác nhận rằng tệp PNG xuất hiện ở vị trí bạn đã chỉ định. Sử dụng bất kỳ ứng dụng đọc mã vạch nào hỗ trợ Macro PDF417 để xác nhận rằng siêu dữ liệu đã được nhúng đúng.

## Các biến thể phổ biến và trường hợp đặc biệt

- **Định dạng hình ảnh khác**: Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp` hoặc `Tiff` nếu hệ thống downstream của bạn ưu tiên định dạng khác.  
- **Thay đổi kích thước mô-đun**: Giá trị `XDimension.Pixels` lớn hơn cải thiện độ tin cậy khi quét trên máy quét độ phân giải thấp nhưng làm tăng kích thước hình ảnh.  
- **Nhiều đoạn**: Để tạo tệp đa đoạn, tạo một loạt mã vạch, tăng `MacroPdf417SegmentID` cho mỗi đoạn và giữ `MacroPdf417FileID` cố định. Chỉ đoạn cuối cùng mới nên có `MacroPdf417Terminator` được đặt.  
- **Hỗ trợ Unicode**: Trình tạo tự động mã hoá ký tự Unicode; đảm bảo chuỗi nguồn của bạn sử dụng mã hoá UTF-8 nếu đọc từ tệp bên ngoài.  
- **Xử lý lỗi**: Bao bọc khối `using` trong try‑catch để bắt `BarCodeException` cho các tham số không hợp lệ (ví dụ, số cột vượt phạm vi).

## Mẹo chuyên nghiệp

- **Hiệu năng**: Tái sử dụng một thể hiện `BarcodeGenerator` duy nhất khi tạo nhiều mã vạch với cùng cài đặt; chỉ thay đổi thuộc tính `CodeText` giữa các lần lưu.  
- **Ước tính kích thước tệp**: Trường `MacroPdf417FileSize` nên khớp với số byte của payload gốc; sự không khớp có thể gây lỗi xác thực downstream.  
- **Kiểm thử**: Xác thực các mã vạch đã tạo bằng cả bộ giải mã tích hợp của Aspose (`BarCodeReader`) và một máy quét bên thứ ba để đảm bảo khả năng tương thích.

## Kết luận

Ví dụ **Aspose.BarCode** này cho bạn thấy cách **tạo mã vạch PDF417 C#** với hỗ trợ đầy đủ siêu dữ liệu Macro, cung cấp nền tảng vững chắc để xây dựng các pipeline trao đổi dữ liệu dựa trên mã vạch mạnh mẽ.

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ code hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch – PDF417 Compact với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách tạo vùng yên tĩnh cho mã Code 16K bằng Aspose.BarCode cho .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Cách tạo vùng yên tĩnh cho mã ITF-14 bằng Aspose.BarCode cho .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**Cập nhật lần cuối:** 2026-10-09  
**Kiểm tra với:** Aspose.BarCode 24.11 for .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách tạo hình ảnh mã vạch Pdf417 trong C với Aspose](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cách tạo mã vạch – PDF417 Compact với Aspose.BarCode](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Hướng dẫn Trình tạo Mã vạch – Cách tạo mã vạch Pdf417](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}