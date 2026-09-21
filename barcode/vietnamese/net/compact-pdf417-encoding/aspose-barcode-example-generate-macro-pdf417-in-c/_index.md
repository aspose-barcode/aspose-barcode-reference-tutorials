---
category: general
date: 2026-08-09
description: Ví dụ mã vạch Aspose cho thấy cách sử dụng trình tạo mã vạch C# để tạo
  Macro PDF417 với hỗ trợ đầy đủ siêu dữ liệu.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: vi
lastmod: 2026-08-09
og_description: Ví dụ mã vạch Aspose trình bày cách sử dụng trình tạo mã vạch C# để
  tạo mã Macro PDF417 bao gồm ID tệp, dữ liệu phân đoạn, dấu thời gian và các siêu
  dữ liệu khác.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Ví dụ mã vạch Aspose – tạo Macro PDF417 bằng C#
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: 'Ví dụ mã vạch Aspose: tạo Macro PDF417 trong C#'
url: /vi/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ví dụ Aspose Barcode: tạo Macro PDF417 bằng C#

Nếu bạn cần một **aspose barcode example** tạo ra một mã vạch Macro PDF417, hướng dẫn này sẽ chỉ cho bạn cách thực hiện bằng **barcode generator C#**. Bạn sẽ thấy mọi cài đặt cần thiết, từ kích thước cơ bản đến toàn bộ các trường metadata của Macro PDF417, và cuối cùng sẽ có một hình ảnh PNG sẵn sàng cho quá trình xử lý tiếp theo.

Bài hướng dẫn bao gồm toàn bộ quy trình, giải thích lý do mỗi tham số quan trọng, và cung cấp một mẫu mã sẵn sàng chạy. Không cần tham chiếu bên ngoài; bạn có thể sao chép mã, điều chỉnh các giá trị và chạy ngay lập tức.

## Yêu cầu trước

- .NET 6.0 (hoặc mới hơn) đã được cài đặt  
- Visual Studio 2022 hoặc bất kỳ IDE nào hỗ trợ C#  
- Giấy phép hợp lệ cho **Aspose.BarCode for .NET** (bản dùng thử miễn phí cũng hoạt động cho ví dụ này)  

Add the Aspose.BarCode NuGet package to your project:

```bash
dotnet add package Aspose.BarCode
```

## Bước 1: Tạo thể hiện barcode generator C# instance

Bước đầu tiên là khởi tạo `BarcodeGenerator` với giá trị enum `EncodeTypes.MacroPdf417` và văn bản bạn muốn mã hoá. Văn bản có thể chứa ký tự Unicode, thư viện sẽ tự động xử lý.

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*Tại sao điều này quan trọng*: `EncodeTypes.MacroPdf417` chỉ cho engine tạo ra một ký hiệu Macro PDF417, hỗ trợ dữ liệu phân đoạn và metadata ở mức tệp bổ sung. Câu lệnh `using` đảm bảo các tài nguyên không quản lý được giải phóng sau khi hình ảnh được lưu.

## Bước 2: Định nghĩa giao diện cơ bản của mã vạch

Mã vạch Macro PDF417 bao gồm các mô-đun hình vuông. Kiểm soát kích thước mô-đun và số cột ảnh hưởng đến độ đọc được và kích thước tệp.

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*Tại sao điều này quan trọng*: `XDimension.Pixels` xác định mật độ hiển thị; giá trị 2 pixel hoạt động tốt cho hiển thị trên màn hình đồng thời giữ hình ảnh nhỏ. Điều chỉnh số cột để phù hợp với ràng buộc bố cục—nhiều cột hơn tạo ra mã vạch rộng hơn, ngắn hơn.

## Bước 3: Đặt metadata đặc thù cho Macro PDF417

Macro PDF417 mở rộng định dạng PDF417 tiêu chuẩn bằng các trường cho phép tái tạo các tệp lớn từ nhiều đoạn mã vạch. Mỗi trường là tùy chọn, nhưng việc đặt chúng thể hiện đầy đủ khả năng của API.

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
- `MacroPdf417SegmentID` và `MacroPdf417SegmentsCount` cho phép bộ giải mã sắp xếp lại các đoạn đúng thứ tự.  
- `MacroPdf417Checksum` cung cấp kiểm tra tính toàn vẹn nhanh mà không cần giải mã toàn bộ payload.  
- `MacroPdf417FileSize` và `MacroPdf417TimeStamp` cho phép hệ thống downstream xác minh rằng tệp đã tái tạo khớp với bản gốc.  
- `MacroPdf417Addressee` / `MacroPdf417Sender` hữu ích trong các kịch bản logistics hoặc trao đổi tài liệu.  
- Đặt `MacroPdf417Terminator` thành `Set` đánh dấu mã vạch này là đoạn cuối cùng, giúp đơn giản hoá thuật toán tái tạo.

## Bước 4: Lưu hình ảnh mã vạch đã tạo

Cuối cùng, ghi mã vạch ra tệp PNG. Bạn có thể chọn bất kỳ định dạng hỗ trợ nào (`Png`, `Jpeg`, `Bmp`, `Gif`, `Tiff`).

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*Tại sao điều này quan trọng*: PNG giữ nguyên dữ liệu pixel không mất mát, đảm bảo máy quét đọc đúng mẫu mô-đun bạn đã cấu hình. Thay đổi định dạng có thể ảnh hưởng đến chất lượng hình ảnh và kích thước tệp.

### Kết quả mong đợi

Chạy toàn bộ chương trình sẽ tạo một tệp có tên **ExtPDF417Meta.png**. Mở hình ảnh sẽ hiển thị một mã vạch Macro PDF417 hình chữ nhật với văn bản “Åspóse.Barcóde©” đã được mã hoá, và mật độ hiển thị khớp với kích thước X 2‑pixel mà bạn đã đặt. Quét hình ảnh bằng trình đọc hỗ trợ PDF417 sẽ trả về tất cả các trường metadata được định nghĩa ở Bước 3.

## Ví dụ hoàn chỉnh hoạt động

Sao chép đoạn mã dưới đây vào một dự án console mới (`dotnet new console`) và thay thế `YOUR_DIRECTORY` bằng đường dẫn tuyệt đối hoặc tương đối tồn tại trên máy của bạn.

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

Chạy chương trình (`dotnet run`). Sau khi thực thi, kiểm tra xem tệp PNG có xuất hiện ở vị trí bạn đã chỉ định không. Sử dụng bất kỳ ứng dụng đọc mã vạch nào hỗ trợ Macro PDF417 để xác nhận metadata đã được nhúng đúng.

## Các biến thể thường gặp và trường hợp đặc biệt

- **Different image formats**: Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, hoặc `Tiff` nếu hệ thống downstream của bạn ưu tiên định dạng khác.  
- **Changing module size**: Giá trị `XDimension.Pixels` lớn hơn cải thiện độ tin cậy khi quét trên máy quét độ phân giải thấp nhưng làm tăng kích thước hình ảnh.  
- **Multiple segments**: Để tạo tệp đa đoạn, tạo một loạt mã vạch, tăng `MacroPdf417SegmentID` cho mỗi đoạn và giữ `MacroPdf417FileID` cố định. Chỉ đoạn cuối cùng mới nên có `MacroPdf417Terminator` được đặt.  
- **Unicode support**: Trình tạo tự động mã hoá ký tự Unicode; đảm bảo chuỗi nguồn của bạn sử dụng mã hoá UTF‑8 nếu đọc từ tệp bên ngoài.  
- **Error handling**: Bao bọc khối `using` trong một try‑catch để bắt `BarCodeException` cho các tham số không hợp lệ (ví dụ: số cột vượt phạm vi).

## Mẹo chuyên nghiệp

- **Performance**: Tái sử dụng một thể hiện `BarcodeGenerator` duy nhất khi tạo nhiều mã vạch với cùng cài đặt; chỉ thay đổi thuộc tính `CodeText` giữa các lần lưu.  
- **File size estimation**: Trường `MacroPdf417FileSize` nên khớp với số byte của payload gốc; sự không khớp có thể gây lỗi xác thực downstream.  
- **Testing**: Xác thực các mã vạch đã tạo bằng cả bộ giải mã tích hợp của Aspose (`BarCodeReader`) và một trình quét bên thứ ba để đảm bảo tính tương thích.

## Kết luận

Đây là **aspose barcode example**

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoàn chỉnh kèm giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo Barcode – Compact PDF417 với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách tạo vùng yên tĩnh cho Code 16K bằng Aspose.BarCode cho .NET](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [Cách tạo vùng yên tĩnh cho ITF-14 bằng Aspose.BarCode cho .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}