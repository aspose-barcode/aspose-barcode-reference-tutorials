---
category: general
date: 2026-10-18
description: Học cách tạo mã vạch PDF417 trong C# với Aspose.BarCode. Hướng dẫn này
  bao gồm việc tạo PDF417 cơ bản, gọn, macro và micro cùng mã nguồn đầy đủ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to create pdf417
language: vi
lastmod: 2026-10-18
og_description: Tạo mã vạch PDF417 trong C# với Aspose.BarCode. Thực hiện theo hướng
  dẫn này để tạo các mã vạch PDF417 cơ bản, gọn, macro và micro một cách từng bước.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as an image file
og_title: Tạo mã vạch PDF417 trong C# – hướng dẫn đầy đủ Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to create PDF417 barcode in C# with Aspose.BarCode. This
    tutorial covers basic, compact, macro and micro PDF417 generation with full code.
  headline: Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
- aspose
title: Tạo mã vạch PDF417 trong C# bằng Aspose.BarCode – hướng dẫn từng bước
url: /vi/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch PDF417 trong C# bằng Aspose.BarCode – hướng dẫn từng bước

Nếu bạn cần **tạo mã vạch PDF417** trong một ứng dụng .NET, hướng dẫn này sẽ dẫn bạn qua toàn bộ quá trình. Bạn sẽ thấy cách tạo một mã vạch cơ bản, bật chế độ compact, thêm siêu dữ liệu macro, và tạo phiên bản micro — tất cả với các giải thích rõ ràng và mã có thể chạy được.

Việc tạo mã vạch PDF417 thường gặp trong logistics, bán vé và quản lý tài liệu. Khi kết thúc hướng dẫn này, bạn sẽ có thể tích hợp việc tạo mã vạch vào bất kỳ dự án C# nào mà không cần công cụ bên ngoài.

## Yêu cầu trước

* .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+)
* Visual Studio 2022 hoặc bất kỳ IDE C# nào
* **Aspose.BarCode for .NET** gói NuGet  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Quyền ghi vào thư mục nơi các tệp PNG được tạo sẽ được lưu

Không cần cấu hình bổ sung; thư viện sẽ xử lý tất cả các chi tiết mã hoá mức thấp.

## Bước 1: Tạo mã vạch PDF417 cơ bản

Bước đầu tiên thiết lập một mã vạch PDF417 thông thường với kích thước và số cột tùy chỉnh.

```csharp
using Aspose.BarCode.Generation;

// Initialize the generator for a standard PDF417 barcode
BarcodeGenerator basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

// Adjust the X‑dimension (module width) to 2 pixels for higher resolution
basicGen.Parameters.Barcode.XDimension.Pixels = 2;

// Set the number of columns – three columns keep the barcode compact yet readable
basicGen.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image
basicGen.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**Tại sao các thiết lập này quan trọng**

* `XDimension.Pixels` kiểm soát kích thước vật lý của mỗi phần tử mã vạch. Giá trị 2 tạo ra hình ảnh rõ ràng trên hầu hết màn hình và máy in.
* `Pdf417.Columns` xác định số cột dữ liệu mà mã vạch chứa. Ít cột hơn giảm chiều rộng; nhiều cột hơn tăng khả năng chứa dữ liệu.

Chạy đoạn mã sẽ tạo ra `Pdf417Basic.png`, trông giống một ký hiệu PDF417 tiêu chuẩn với ba cột dữ liệu và một cột siêu dữ liệu đầy đủ ở phía bên phải.

## Bước 2: Bật chế độ compact (rút gọn)

Chế độ compact loại bỏ cột siêu dữ liệu bên phải, làm cho mã vạch hẹp hơn. Điều này hữu ích khi không gian hạn chế nhưng dữ liệu vẫn có thể được tái tạo từ các hàng còn lại.

```csharp
// Turn on truncated mode to omit the metadata column
basicGen.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version
basicGen.Save(@"YOUR_DIRECTORY\CompactPdf417.png", BarCodeImageFormat.Png);
```

**Tại sao phải rút gọn?**  
Khi `Truncate` là `true`, trình tạo sẽ bỏ qua cột bên phải tùy chọn lưu trữ dữ liệu sửa lỗi và siêu dữ liệu cấp tệp. Mã vạch tạo ra chiếm ít cột hơn trong khi vẫn có thể quét được bởi hầu hết các trình đọc PDF417.

## Bước 3: Tạo mã vạch Macro PDF417 với siêu dữ liệu cấp tệp

Macro PDF417 mở rộng định dạng tiêu chuẩn bằng các định danh đoạn, cho phép một tài liệu lớn được chia thành nhiều mã vạch. Điều này tiện lợi cho việc mã hoá các chuỗi dài hoặc tệp đa trang.

```csharp
// Initialize a generator for Macro PDF417
BarcodeGenerator macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");

// Set column count for better readability
macroGen.Parameters.Barcode.Pdf417.Columns = 5;

// Assign macro-specific identifiers
macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Unique file identifier
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;      // Current segment number
macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total segments

// Save the macro barcode
macroGen.Save(@"YOUR_DIRECTORY\MacroPdf417.png", BarCodeImageFormat.Png);
```

**Giải thích các trường macro**

| Property | Purpose |
|----------|---------|
| `MacroPdf417FileID` | Mã định danh duy nhất cho toàn bộ tệp; tất cả các đoạn chia sẻ giá trị này. |
| `MacroPdf417SegmentID` | Chỉ mục của đoạn hiện tại (bắt đầu từ 1). |
| `MacroPdf417SegmentsCount` | Tổng số đoạn tạo thành bộ dữ liệu hoàn chỉnh. |

Một máy quét hiểu Macro PDF417 có thể ghép lại dữ liệu gốc bằng cách đọc tất cả các đoạn và sử dụng các định danh này.

## Bước 4: Tạo mã vạch Micro PDF417 cho dữ liệu ngắn

Micro PDF417 là phiên bản gọn nhẹ được thiết kế cho tải trọng nhỏ (tối đa 90 ký tự). Nó giới hạn phạm vi cột từ 1‑4, làm cho mã vạch phù hợp cho các nhãn nhỏ hoặc thiết bị có khu vực hiển thị hạn chế.

```csharp
// Initialize a generator for Micro PDF417
BarcodeGenerator microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");

// Set a fine X‑dimension for crisp rendering
microGen.Parameters.Barcode.XDimension.Pixels = 2;

// Choose a column count within the allowed range (1‑4)
microGen.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode
microGen.Save(@"YOUR_DIRECTORY\MicroPdf417.png", BarCodeImageFormat.Png);
```

**Khi nào nên dùng Micro PDF417**  
Sử dụng phiên bản này khi tải dữ liệu ngắn và bạn cần mã vạch nhỏ nhất có thể. Nó lý tưởng cho thẻ kho, thẻ truy cập, hoặc bất kỳ trường hợp nào mà không gian hiển thị là rất hạn chế.

## Ví dụ làm việc đầy đủ

Dưới đây là một ứng dụng console tự chứa, tạo ra tất cả bốn loại mã vạch trong một lần chạy. Sao chép mã vào một dự án C# mới, thay thế `YOUR_DIRECTORY` bằng đường dẫn thư mục hiện có, và chạy nó.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Adjust this path to a writable folder on your machine
            string outputPath = @"C:\Barcodes";

            // ---------- Basic PDF417 ----------
            var basicGen = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            basicGen.Parameters.Barcode.XDimension.Pixels = 2;
            basicGen.Parameters.Barcode.Pdf417.Columns = 3;
            basicGen.Save($"{outputPath}\\Pdf417Basic.png", BarCodeImageFormat.Png);

            // ---------- Compact PDF417 ----------
            basicGen.Parameters.Barcode.Pdf417.Truncate = true;
            basicGen.Save($"{outputPath}\\CompactPdf417.png", BarCodeImageFormat.Png);

            // ---------- Macro PDF417 ----------
            var macroGen = new BarcodeGenerator(EncodeTypes.MacroPdf417, "sample text");
            macroGen.Parameters.Barcode.Pdf417.Columns = 5;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
            macroGen.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
            macroGen.Save($"{outputPath}\\MacroPdf417.png", BarCodeImageFormat.Png);

            // ---------- Micro PDF417 ----------
            var microGen = new BarcodeGenerator(EncodeTypes.MicroPdf417, "small data");
            microGen.Parameters.Barcode.XDimension.Pixels = 2;
            microGen.Parameters.Barcode.Pdf417.Columns = 4; // valid range: 1‑4
            microGen.Save($"{outputPath}\\MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("All PDF417 barcodes have been generated successfully.");
        }
    }
}
```

**Kết quả mong đợi**

Chạy chương trình sẽ tạo ra bốn tệp PNG trong thư mục đã chỉ định:

* `Pdf417Basic.png` – mã vạch tiêu chuẩn với ba cột
* `CompactPdf417.png` – cùng dữ liệu, cột bên phải đã bị rút gọn
* `MacroPdf417.png` – mã vạch macro chứa siêu dữ liệu đoạn
* `MicroPdf417.png` – mã vạch micro gọn cho chuỗi ngắn

Mở bất kỳ hình ảnh nào bằng trình xem ảnh; bạn sẽ thấy các mẫu PDF417 đặc trưng. Quét chúng bằng một trình đọc mã vạch di động (ví dụ: ZXing, Scandit) sẽ trả về các chuỗi văn bản gốc.

## Câu hỏi thường gặp và mẹo

* **Nếu mã vạch bị mờ thì sao?**  
  Tăng `XDimension.Pixels` lên 3 hoặc 4. Kích thước mô-đun lớn hơn tạo ra hình ảnh độ phân giải cao hơn, nhưng kích thước tệp sẽ lớn hơn.

* **Tôi có thể xuất SVG thay vì PNG không?**  
  Có. Thay thế `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Svg` trong các lời gọi `Save`.

* **Có cần thiết lập mức sửa lỗi (error‑correction) thủ công không?**  
  Aspose.BarCode tự động chọn mức tối ưu. Đối với các trường hợp sử dụng đặc biệt, bạn có thể điều chỉnh `Pdf417.ErrorCorrectionLevel`.

* **Làm thế nào để nhúng mã vạch vào tài liệu PDF?**  
  Sử dụng `Aspose.Pdf` để thêm PNG hoặc SVG đã tạo làm phần tử hình ảnh trên một trang PDF.

* **Thư viện có an toàn với đa luồng không?**  
  Mỗi thể hiện `BarcodeGenerator` là độc lập; bạn có thể tạo các generator trên nhiều luồng mà không có trạng thái chung.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch PDF417** trong C# bằng Aspose.BarCode, bao gồm các biến thể cơ bản, compact, macro và micro.

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch pdf417 trong C# – hướng dẫn từng bước](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [Cách tạo mã vạch PDF417 trong C# với chế độ compact](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Cách tạo mã vạch macro PDF417 trong C# bằng Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}