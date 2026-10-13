---
category: general
date: 2026-09-29
description: Cách lưu mã vạch bằng Aspose.BarCode trong C# và học cách tạo PDF417
  với siêu dữ liệu macro. Thực hiện theo hướng dẫn từng bước.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- how to generate pdf417
- how to set pdf417
- generate barcode with aspose
language: vi
lastmod: 2026-09-29
og_description: Cách lưu mã vạch bằng Aspose.BarCode trong C# rất đơn giản. Hướng
  dẫn này cho thấy cách tạo PDF417 với siêu dữ liệu macro và thiết lập tất cả các
  tham số cần thiết.
og_image_alt: Screenshot showing how to save barcode as PNG with PDF417 macro metadata
og_title: Cách lưu mã vạch với Aspose – Hướng dẫn tạo PDF417
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  headline: How to save barcode and generate PDF417 with Aspose in C#
  type: TechArticle
- description: How to save barcode using Aspose.BarCode in C# and learn how to generate
    PDF417 with macro metadata. Follow step‑by‑step guide.
  name: How to save barcode and generate PDF417 with Aspose in C#
  steps:
  - name: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
    text: '**Creating the generator** – The `BarcodeGenerator` constructor takes the
      barcode type (`EncodeTypes.MacroPdf417`) and the data to encode. Macro PDF417
      is a special variant that carries file‑transfer information, which is why we
      later fill macro fields.'
  - name: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
    text: '**Appearance settings** – `XDimension.Pixels` controls the narrow bar width;
      adjusting it changes the overall image size without affecting data integrity.
      `Pdf417.Columns` defines the layout of the barcode matrix.'
  - name: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
    text: '**Macro metadata** – These properties (`MacroPdf417FileID`, `MacroPdf417SegmentID`,
      etc.) are essential when you need to split a large file into multiple barcode
      segments. Setting them correctly ensures that a scanner can reconstruct the
      original file.'
  - name: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
    text: '**Saving the image** – The `Save` method writes the generated barcode to
      disk. You can choose any supported format (`Png`, `Jpeg`, `Bmp`, etc.). This
      line demonstrates the exact **how to save barcode** operation requested.'
  type: HowTo
tags:
- barcode
- PDF417
- Aspose
- C#
title: Cách lưu mã vạch và tạo PDF417 với Aspose trong C#
url: /vi/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách lưu mã vạch và tạo PDF417 với Aspose trong C#

Cách lưu mã vạch bằng Aspose.BarCode trong C# là một yêu cầu phổ biến khi bạn cần nhúng dữ liệu vào một tệp hình ảnh. Hướng dẫn này sẽ dẫn bạn qua toàn bộ quy trình tạo mã vạch PDF417 với macro‑metadata và lưu kết quả dưới dạng ảnh PNG. Khi kết thúc, bạn sẽ biết **cách tạo PDF417**, **cách thiết lập PDF417**, và quan trọng nhất, **cách lưu mã vạch** một cách lập trình.

Bạn sẽ thấy một ví dụ đầy đủ, có thể chạy ngay, bao gồm mọi bước—từ việc thêm gói NuGet Aspose.BarCode đến cấu hình các trường macro như file ID, segment count và checksum. Không cần tài liệu bên ngoài; mã có thể sao chép vào một dự án console mới và chạy ngay lập tức. Hướng dẫn giả định bạn đã cài Visual Studio 2022 (hoặc mới hơn) và .NET 6.0.

## Prerequisites

- .NET 6.0 SDK (hoặc bất kỳ phiên bản .NET nào được Aspose.BarCode 23.11+ hỗ trợ)
- Visual Studio 2022, VS Code, hoặc IDE C# ưa thích của bạn
- **Aspose.BarCode for .NET** NuGet package  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- Kiến thức cơ bản về cú pháp C# và các ứng dụng console

> **Pro tip:** Sử dụng giấy phép đánh giá miễn phí cho nhà phát triển từ Aspose nếu bạn chưa có giấy phép thương mại. Giấy phép đánh giá hoạt động mà không cần thay đổi mã.

## How to save barcode – complete example

Mã dưới đây tạo một mã **Macro PDF417**, điền đầy đủ các trường macro, và lưu ảnh dưới tên `ExtPDF417Meta.png`. Tất cả các chỉ thị `using` cần thiết đã được bao gồm để bạn có thể dán đoạn mã trực tiếp vào `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for Macro PDF417 with sample data
        using (BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,          // EncodeTypes enum selects the barcode type
            "Åspóse.Barcóde©"))               // Sample data – Unicode characters are supported
        {
            // Step 2: Define basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width (2 px)
            generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns per row

            // Step 3: Configure Macro PDF417 metadata
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Step 4: Save the generated barcode as a PNG image
            // This is the core of **how to save barcode** with Aspose.
            generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Barcode saved as ExtPDF417Meta.png");
    }
}
```

### Why each step matters

1. **Creating the generator** – Hàm khởi tạo `BarcodeGenerator` nhận loại mã vạch (`EncodeTypes.MacroPdf417`) và dữ liệu cần mã hoá. Macro PDF417 là một biến thể đặc biệt mang thông tin chuyển file, vì vậy chúng ta sẽ điền các trường macro sau.
2. **Appearance settings** – `XDimension.Pixels` điều chỉnh độ rộng thanh hẹp; thay đổi giá trị này sẽ thay đổi kích thước tổng thể của ảnh mà không ảnh hưởng tới tính toàn vẹn dữ liệu. `Pdf417.Columns` xác định bố cục ma trận mã vạch.
3. **Macro metadata** – Các thuộc tính này (`MacroPdf417FileID`, `MacroPdf417SegmentID`, …) là thiết yếu khi bạn cần chia một tệp lớn thành nhiều đoạn mã vạch. Đặt chúng đúng sẽ cho phép máy quét tái tạo lại tệp gốc.
4. **Saving the image** – Phương thức `Save` ghi mã vạch đã tạo ra lên đĩa. Bạn có thể chọn bất kỳ định dạng nào được hỗ trợ (`Png`, `Jpeg`, `Bmp`, …). Dòng này minh họa thao tác **cách lưu mã vạch** chính xác mà bạn đang tìm kiếm.

> **Common question:** *What if I need a different image format?*  
> Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg` (hoặc bất kỳ giá trị enum nào khác được hỗ trợ) và điều chỉnh phần mở rộng tệp cho phù hợp.

## How to generate PDF417 with macro metadata

Nếu bạn chỉ cần một PDF417 thông thường (không có dữ liệu macro), bạn có thể bỏ qua phần macro và giữ lại generator cơ bản:

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 3;
    gen.Save("SimplePdf417.png", BarCodeImageFormat.Png);
}
```

Đoạn mã trên minh họa **cách tạo PDF417** nhanh chóng. Lưu ý rằng enum `EncodeTypes.Pdf417` chọn phiên bản không có macro.

## How to set PDF417 – advanced options

Aspose.BarCode cung cấp nhiều tham số chuyên dụng cho PDF417. Dưới đây là một vài tham số bạn có thể cần:

| Thuộc tính | Mô tả | Giá trị điển hình |
|------------|------|-------------------|
| `Pdf417.Columns` | Số cột trên mỗi hàng | 1‑30 (mặc định 3) |
| `Pdf417.Rows` | Số hàng (tự động tính nếu bằng 0) | 0‑90 |
| `Pdf417.ErrorLevel` | Mức độ sửa lỗi (0‑8) | 2‑4 cho cân bằng kích thước/độ bền |
| `Pdf417.RowsPerStrip` | Số hàng mỗi dải cho mã vạch lớn | 0 (tự động) |
| `Pdf417.Pdf417MacroFileID` | Định danh cho tệp khi sử dụng macro | Bất kỳ số nguyên 32‑bit nào |

Việc thiết lập các giá trị này tuân theo cùng một mẫu như trong **Bước 2** của ví dụ chính. Điều chỉnh chúng trước khi gọi `Save`.

## Expected output

Chạy toàn bộ chương trình sẽ tạo ra tệp `ExtPDF417Meta.png` trong thư mục làm việc của executable. Ảnh chứa một mã vạch PDF417 độ phân giải cao với tất cả các trường macro được nhúng. Quét ảnh này bằng một máy quét hỗ trợ PDF417 (hoặc ứng dụng di động) sẽ trả về chuỗi dữ liệu gốc `"Åspóse.Barcóde©"` cùng với metadata macro (file ID, segment ID, …).

![Barcode saved as PNG – how to save barcode example](ExtPDF417Meta.png "How to save barcode as PNG with macro PDF417 metadata")

*Image alt text:* **how to save barcode as PNG with PDF417 macro metadata** (matches primary keyword).

## Conclusion

Trong tutorial này bạn đã học **cách lưu mã vạch** bằng Aspose.BarCode, **cách tạo PDF417**, **cách thiết lập PDF417** và **cách tạo mã vạch với Aspose** cho cả trường hợp thông thường và có macro.

## What Should You Learn Next?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm mã mẫu hoàn chỉnh cùng các giải thích chi tiết từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to generate barcode in C# with Aspose.BarCode and add metadata](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode-and-add-met/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}