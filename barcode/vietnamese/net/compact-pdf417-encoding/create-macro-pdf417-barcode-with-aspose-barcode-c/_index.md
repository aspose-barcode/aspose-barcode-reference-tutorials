---
category: general
date: 2026-09-22
description: Tạo mã vạch macro PDF417 bằng Aspose.BarCode trong C#. Học cách từng
  bước tạo mã vạch với Aspose, cấu hình siêu dữ liệu và lưu dưới dạng PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: vi
lastmod: 2026-09-22
og_description: Tạo mã vạch macro PDF417 bằng Aspose.BarCode trong C#. Hướng dẫn này
  chỉ cho bạn cách tạo mã vạch với Aspose, thiết lập siêu dữ liệu macro và xuất hình
  ảnh.
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: Tạo mã vạch macro PDF417 bằng Aspose.BarCode (C#) – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: Tạo mã vạch macro PDF417 với Aspose.BarCode (C#)
url: /vi/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo macro PDF417 barcode với Aspose.BarCode (C#)

Nếu bạn cần **tạo macro PDF417 barcode** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chính xác bằng Aspose.BarCode. Bạn sẽ thấy một ví dụ hoàn chỉnh, có thể chạy được mà **generates barcode with Aspose**, cấu hình tất cả các trường đặc thù của macro, và lưu kết quả dưới dạng ảnh PNG.

Mã vạch thường được sử dụng cho quản lý tồn kho, vận chuyển, hoặc theo dõi tài liệu, và phiên bản Macro PDF417 cho phép bạn nhúng siêu dữ liệu cấp tệp bổ sung bên trong mã vạch. Khi kết thúc hướng dẫn này, bạn sẽ có thể tạo một macro PDF417 barcode đầy đủ tính năng, tuân thủ tiêu chuẩn ISO/IEC 15438.

## Những gì bạn cần

* .NET 6.0 SDK hoặc phiên bản mới hơn (mã hoạt động với .NET Core và .NET Framework)
* Visual Studio 2022 (hoặc bất kỳ IDE C# nào)
* Kết nối internet tương thích với NuGet để tải gói Aspose.BarCode
* Kiến thức cơ bản về cú pháp C#

Các yêu cầu này đảm bảo mã biên dịch mà không cần cấu hình thêm.

## Bước 1: Cài đặt gói NuGet Aspose.BarCode

Thư viện Aspose.BarCode cung cấp lớp `BarcodeGenerator` được sử dụng xuyên suốt hướng dẫn này.

```bash
dotnet add package Aspose.BarCode
```

Chạy lệnh sẽ thêm phiên bản ổn định mới nhất vào tệp dự án của bạn (`*.csproj`). Gói này hỗ trợ PDF417, Macro PDF417 và nhiều loại mã vạch khác.

## Bước 2: Tạo dự án console mới (tùy chọn)

Nếu bạn muốn bắt đầu sạch sẽ, tạo một ứng dụng console:

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

Tệp `Program.cs` được tạo sẽ chứa mã tạo barcode.

## Bước 3: Khởi tạo trình tạo mã vạch

Trình tạo được tạo bằng giá trị enum `EncodeTypes.MacroPdf417` và văn bản bạn muốn mã hoá. Aspose.BarCode tự động xử lý ký tự Unicode, vì vậy bạn có thể bao gồm các chữ có dấu hoặc ký hiệu trực tiếp.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### Tại sao điều này quan trọng
`EncodeTypes.MacroPdf417` cho thư viện biết sử dụng phiên bản macro của PDF417, bổ sung khả năng nhúng siêu dữ liệu cấp tệp (file ID, segment count, v.v.). Văn bản `"Åspóse.Barcóde©"` minh họa rằng trình tạo mã hoá đúng ký tự UTF‑8.

## Bước 4: Đặt kích thước cơ bản cho mã vạch

PDF417 cho phép bạn kiểm soát số cột và X‑dimension (độ rộng của một mô-đun). Điều chỉnh các giá trị này ảnh hưởng đến kích thước vật lý của mã vạch và độ tin cậy khi quét.

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – Giá trị nhỏ hơn tạo mã vạch dày đặc hơn; giá trị lớn hơn giúp máy quét độ phân giải thấp dễ đọc hơn.
* **Columns** – Điều khiển số cột dữ liệu; giá trị thường nằm trong khoảng từ 1 đến 30.

## Bước 5: Cấu hình siêu dữ liệu Macro PDF417

Macro PDF417 chứa các trường bổ sung mô tả tệp mà mã vạch đại diện. Mỗi trường là tùy chọn, nhưng việc thiết lập chúng cải thiện khả năng tương thích với các máy quét hiểu định dạng macro.

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### Giải thích từng trường

| Thuộc tính | Mục đích | Phạm vi điển hình |
|------------|----------|-------------------|
| **MacroPdf417FileID** | Mã định danh duy nhất cho tệp logic có thể được chia thành nhiều mã vạch. | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | Chỉ mục của đoạn hiện tại (bắt đầu từ 0). | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | Tổng số đoạn tạo thành tệp đầy đủ. | 1‑99 |
| **MacroPdf417FileName** | Tên tệp có thể đọc được bởi con người. | Up to 255 characters |
| **MacroPdf417Checksum** | Checksum tùy chọn để phát hiện lỗi. | 0‑65535 |
| **MacroPdf417FileSize** | Kích thước của tệp gốc tính bằng byte. | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | Dấu thời gian tạo hoặc sửa đổi tệp. | Any `DateTime` |
| **MacroPdf417Addressee** | Định danh người nhận (ví dụ: phòng ban hoặc máy). | Free‑form string |
| **MacroPdf417Sender** | Định danh người gửi (ví dụ: tên công ty). | Free‑form string |
| **MacroPdf417Terminator** | Cho biết đoạn này có phải là đoạn cuối cùng hay không. | `Set` or `Unset` |

**Pro tip:** Nếu bạn chia một tệp lớn thành nhiều mã vạch, hãy đảm bảo mỗi `SegmentID` của đoạn là tuần tự và `SegmentsCount` giữ nguyên trên tất cả các đoạn. Máy quét dựa vào các giá trị này để tái tạo lại tệp gốc.

## Bước 6: Lưu ảnh mã vạch

Aspose.BarCode hỗ trợ nhiều định dạng xuất (PNG, JPEG, BMP, SVG, v.v.). PNG cung cấp chất lượng không mất dữ liệu, lý tưởng cho việc thử nghiệm và tài liệu.

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

Chạy chương trình sẽ tạo tệp có tên `ExtPDF417Meta.png` trong thư mục đầu ra của dự án (`bin/Debug/net6.0/`). Mở ảnh bằng bất kỳ trình xem nào để xác nhận mã vạch được hiển thị đúng.

## Bước 7: Xác minh mã vạch đã tạo (tùy chọn)

Nếu bạn có ứng dụng quét PDF417 (di động hoặc desktop), quét PNG đã lưu. Máy quét nên trả về:

* Văn bản đã mã hoá `"Åspóse.Barcóde©"`
* Tất cả các trường macro bạn đã cấu hình (file ID, segment ID, v.v.)

Đối với kiểm tra tự động, Aspose.BarCode cũng cung cấp lớp `BarCodeReader`:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

Đoạn mã này minh họa cách đọc lại siêu dữ liệu macro một cách lập trình, xác nhận rằng **generate barcode with Aspose** hoạt động end‑to‑end.

## Các trường hợp đặc biệt và thực tiễn tốt nhất

| Tình huống | Xử lý đề xuất |
|-----------|----------------|
| **Unicode characters** | Đảm bảo chuỗi nguồn là UTF‑8 (mặc định trong .NET). Aspose.BarCode tự động mã hoá Unicode, nhưng hãy kiểm tra bộ mã ký tự của máy quét. |
| **Large file size** | Macro PDF417 chia tệp thành tối đa 99 đoạn. Nếu tệp vượt quá 400 KB, tăng `SegmentsCount` và tạo nhiều mã vạch, mỗi mã có `SegmentID` tuần tự. |
| **Timestamp precision** | Sử dụng `DateTime.UtcNow` cho thời gian toàn cầu; một số máy quét mong đợi thời gian UTC. |
| **Checksum validation** | Cung cấp checksum chính xác nếu bạn dự định kiểm tra tính toàn vẹn ở phía nhận. |
| **Different image formats** | Sử dụng `BarCodeImageFormat.Svg` cho đồ họa vector khi bạn cần mã vạch có thể phóng to vô hạn. |
| **Performance** | Tái sử dụng một thể hiện `BarcodeGenerator` duy nhất khi tạo nhiều mã vạch; chỉ thay đổi `Parameters` giữa các vòng lặp. |

## Ví dụ đầy đủ, có thể chạy

Dưới đây là chương trình hoàn chỉnh bạn có thể sao chép, dán và chạy mà không cần chỉnh sửa (giả sử gói NuGet đã được cài đặt).



## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Ví dụ Aspose barcode: tạo Macro PDF417 trong C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [Tạo siêu dữ liệu mã vạch PDF417 trong C# – Hướng dẫn chi tiết từng bước](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Cách tạo ảnh mã vạch PDF417 trong C# với Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}