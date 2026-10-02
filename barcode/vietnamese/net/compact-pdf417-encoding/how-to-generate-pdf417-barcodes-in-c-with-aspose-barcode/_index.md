---
category: general
date: 2026-09-10
description: Cách tạo mã vạch PDF417 trong C# bằng Aspose.BarCode. Thực hiện theo
  hướng dẫn từng bước để tạo Macro PDF417, điều chỉnh các tham số và xuất ra PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- macro pdf417 barcode
- aspose.barcode for .net
- c# barcode generator
- pdf417 barcode parameters
- barcode image export
language: vi
lastmod: 2026-09-10
og_description: Cách tạo mã vạch PDF417 trong C# với Aspose.BarCode. Tìm hiểu quy
  trình đầy đủ từ cài đặt đến lưu hình ảnh PNG Macro PDF417.
og_image_alt: Screenshot of a generated Macro PDF417 barcode saved as a PNG file
og_title: Cách tạo mã vạch PDF417 trong C# – hướng dẫn đầy đủ Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  headline: How to generate PDF417 barcodes in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate PDF417 barcodes in C# using Aspose.BarCode. Follow
    a step‑by‑step guide to create Macro PDF417, adjust parameters, and export as
    PNG.
  name: How to generate PDF417 barcodes in C# with Aspose.BarCode
  steps:
  - name: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
    text: '**Create a Macro PDF417 generator** – `EncodeTypes.MacroPdf417` tells Aspose.BarCode
      to use the macro version of PDF417, which supports splitting a large payload
      across multiple symbols.'
  - name: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
    text: '**Adjust basic appearance** – `XDimension` controls the module (dot) width;
      `Columns` defines how many columns each symbol will contain, influencing both
      size and readability.'
  - name: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
    text: '**Set macro‑specific fields** – These properties (`MacroPdf417FileID`,
      `MacroPdf417SegmentID`, etc.) are required by the PDF417 macro specification
      to re‑assemble the original data on the scanner side.'
  - name: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
    text: '**Export the image** – `BarCodeImageFormat.Png` provides a lossless image
      that works well for web, print, and mobile scenarios.'
  - name: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
    text: '**Visual verification** – Open `MacroPdf417.png` in any image viewer. You
      should see a stacked set of vertical bars with a small text caption (the encoded
      data).'
  - name: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
    text: '**Scanner test** – Use a mobile barcode scanner app that supports PDF417.
      Scan the image; the app should return the original “Sample text” plus macro
      metadata (file ID, segment ID, etc.).'
  - name: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
    text: '**Error handling** – If the scanner reports “checksum error,” double‑check
      `MacroPdf417Checksum` and ensure the `MacroPdf417Terminator` is set correctly
      on the last segment.'
  - name: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
    text: '**Performance** – Generating many segments in a loop can be CPU‑intensive.
      Re‑use a single `BarcodeGenerator` instance and only update the macro fields
      between saves to improve throughput.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- aspose
title: Cách tạo mã vạch PDF417 trong C# với Aspose.BarCode
url: /vi/net/compact-pdf417-encoding/how-to-generate-pdf417-barcodes-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 trong C# với Aspose.BarCode

Nếu bạn cần **cách tạo pdf417** trong một dự án .NET, hướng dẫn này sẽ trình bày quy trình hoàn chỉnh. Bạn sẽ thấy cách tạo mã vạch Macro PDF417, tinh chỉnh các thiết lập, và xuất kết quả dưới dạng ảnh PNG—tất cả đều sử dụng Aspose.BarCode cho .NET.

Việc tạo mã vạch PDF417 phổ biến trong logistics, bán vé và quy trình tài liệu bảo mật. Khi kết thúc hướng dẫn, bạn sẽ có một trình tạo mã vạch C# sẵn sàng sử dụng, có thể đưa vào bất kỳ ứng dụng nào.

## Những gì bạn cần

- **Visual Studio 2022** (hoặc bất kỳ IDE C# nào)  
- **.NET 6.0** trở lên  
- Gói NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)  
- Kiến thức cơ bản về cú pháp C#  

> **Mẹo chuyên nghiệp:** Sử dụng phiên bản Aspose.BarCode mới nhất để có các tính năng Macro PDF417 mới nhất và các bản sửa lỗi.

---

## Cách tạo mã vạch PDF417 trong C#  

Dưới đây là một ví dụ có thể chạy được đầy đủ, tạo mã vạch **Macro PDF417**, cấu hình các trường đặc thù của macro, và lưu ảnh.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // STEP 1 – create a Macro PDF417 generator with the desired text
        using (BarcodeGenerator generator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // STEP 2 – adjust basic barcode appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 5;     // number of columns

            // STEP 3 – configure Macro PDF417 specific fields
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2023, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // STEP 4 – save the generated barcode as a PNG image
            generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
        }

        Console.WriteLine("Macro PDF417 barcode generated: MacroPdf417.png");
    }
}
```

### Tại sao mỗi bước lại quan trọng

1. **Tạo trình tạo Macro PDF417** – `EncodeTypes.MacroPdf417` báo cho Aspose.BarCode sử dụng phiên bản macro của PDF417, cho phép chia một payload lớn thành nhiều ký hiệu.  
2. **Điều chỉnh giao diện cơ bản** – `XDimension` kiểm soát độ rộng mô-đun (điểm); `Columns` xác định số cột mỗi ký hiệu sẽ chứa, ảnh hưởng đến kích thước và khả năng đọc.  
3. **Đặt các trường đặc thù của macro** – Các thuộc tính này (`MacroPdf417FileID`, `MacroPdf417SegmentID`, …) là bắt buộc theo chuẩn PDF417 macro để tái tạo dữ liệu gốc ở phía máy quét.  
4. **Xuất ảnh** – `BarCodeImageFormat.Png` cung cấp ảnh không mất dữ liệu, phù hợp cho web, in ấn và thiết bị di động.

---

## Cài đặt Aspose.BarCode cho .NET (trình tạo mã vạch C#)

Trước khi chạy đoạn mã ở trên, bạn phải thêm thư viện Aspose.BarCode vào dự án:

```bash
dotnet add package Aspose.BarCode
```

*Gói NuGet bao gồm tất cả các phụ thuộc, vì vậy không cần DLL bổ sung nào.*  
Nếu bạn nhắm tới .NET Framework, lệnh `Install-Package Aspose.BarCode` vẫn hoạt động từ Package Manager Console.

### Những lỗi thường gặp

- **Thiếu giấy phép** – Mặc định Aspose chạy ở chế độ đánh giá, sẽ thêm watermark vào mã vạch. Đăng ký file giấy phép (`License license = new License(); license.SetLicense("Aspose.BarCode.lic");`) để loại bỏ watermark.  
- **`EncodeTypes` không đúng** – Sử dụng `EncodeTypes.Pdf417` thay vì `EncodeTypes.MacroPdf417` sẽ bỏ qua tất cả các trường macro, làm hỏng việc tái tạo đa đoạn.

---

## Cấu hình các tham số mã vạch Macro PDF417

Các trường macro cho phép bạn chia một tài liệu lớn thành nhiều ký hiệu PDF417. Dưới đây là bảng tham khảo nhanh:

| Property | Purpose | Typical range |
|----------|---------|---------------|
| `MacroPdf417FileID` | Định danh duy nhất cho toàn bộ tệp | 0‑2³¹‑1 |
| `MacroPdf417SegmentID` | Chỉ mục của đoạn hiện tại (bắt đầu từ 0) | 0‑254 |
| `MacroPdf417SegmentsCount` | Tổng số đoạn trong tệp | 1‑255 |
| `MacroPdf417FileName` | Tên đọc được bởi con người (tùy chọn) | 0‑255 ký tự |
| `MacroPdf417Checksum` | Kiểm tra lỗi CCITT‑16 | 0‑65535 |
| `MacroPdf417FileSize` | Kích thước tệp gốc tính bằng byte | 0‑2³¹‑1 |
| `MacroPdf417TimeStamp` | Thời gian tạo (tùy chọn) | Giá trị `DateTime` |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Siêu dữ liệu tùy chọn cho việc định tuyến | Bất kỳ chuỗi nào |
| `MacroPdf417Terminator` | Chỉ ra đoạn cuối cùng (`Set` hoặc `Unset`) | Enum `Pdf417MacroTerminator` |

Điều chỉnh các giá trị này sao cho phù hợp với dữ liệu bạn đang mã hoá. Ví dụ, nếu bạn chia một tệp 2 MB thành 20 đoạn, đặt `MacroPdf417FileSize` thành `2_000_000` và `MacroPdf417SegmentsCount` thành `20`.

---

## Xuất mã vạch dưới dạng ảnh PNG (xuất ảnh mã vạch)

Lưu mã vạch dưới dạng PNG là định dạng xuất khẩu phổ biến nhất vì nó giữ được các cạnh sắc nét và hỗ trợ trong suốt. Aspose.BarCode cũng hỗ trợ JPEG, BMP, GIF và TIFF—bạn có thể chọn định dạng phù hợp với quy trình downstream.

```csharp
generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
```

**Mẹo để có đầu ra chất lượng cao**

- Tăng `XDimension.Pixels` để có mô-đun lớn hơn khi in trên vật liệu độ phân giải cao.  
- Sử dụng `BarCodeImageFormat.Tiff` với nén CCITT Group 4 cho các PDF tương thích fax.  
- Đặt `generator.Parameters.ImageOptions.Resolution` nếu bạn cần DPI cụ thể (ví dụ, 300 dpi cho in).

---

## Kiểm tra và khắc phục sự cố mã vạch PDF417 của bạn

1. **Kiểm tra trực quan** – Mở `MacroPdf417.png` bằng bất kỳ trình xem ảnh nào. Bạn sẽ thấy một tập hợp các thanh dọc xếp chồng lên nhau cùng một chú thích văn bản nhỏ (dữ liệu đã mã hoá).  
2. **Kiểm tra bằng máy quét** – Dùng ứng dụng quét mã vạch di động hỗ trợ PDF417. Quét ảnh; ứng dụng nên trả về “Sample text” gốc cộng với siêu dữ liệu macro (file ID, segment ID, …).  
3. **Xử lý lỗi** – Nếu máy quét báo “checksum error”, kiểm tra lại `MacroPdf417Checksum` và đảm bảo `MacroPdf417Terminator` được đặt đúng ở đoạn cuối cùng.  
4. **Hiệu năng** – Tạo nhiều đoạn trong vòng lặp có thể tốn CPU. Hãy tái sử dụng một đối tượng `BarcodeGenerator` duy nhất và chỉ cập nhật các trường macro giữa các lần lưu để tăng tốc độ.

---

## Kết luận

Bạn đã biết **cách tạo PDF417** trong C# bằng Aspose.BarCode, từ việc cài đặt thư viện, cấu hình các trường Macro PDF417, đến việc xuất ảnh PNG sạch sẽ. Giải pháp hoàn chỉnh minh họa:

- Thiết lập **trình tạo mã vạch C#** với loại Macro PDF417  
- Tùy chỉnh **các tham số mã vạch PDF417** cho dữ liệu đa đoạn  
- Thực hiện **xuất ảnh mã vạch** cho các mục đích downstream  

Từ đây bạn có thể khám phá các chủ đề nâng cao như nhúng mã vạch vào tài liệu PDF, tạo mã QR‑code đi kèm, hoặc tự động xử lý hàng loạt các tệp lớn.

**Bước tiếp theo**

- Thử các giá trị `BarCodeImageFormat` khác (ví dụ, `Tiff` cho bản in độ phân giải cao).  
- Kết hợp Macro PDF417 với các symbology khác trong cùng một tài liệu bằng `generator.Parameters.Barcode.Symbology`.  
- Xem tài liệu [Aspose.BarCode documentation](https://docs.aspose.com/barcode/net/) để tùy chỉnh sâu hơn như mức độ sửa lỗi và chế độ mã hoá.

Chúc bạn lập trình vui vẻ!


## Bạn nên học gì tiếp theo?


Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Generate barcode with text – Full PDF417 Macro Guide](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [adjust barcode size – C# guide to generate PDF417 barcodes](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}