---
category: general
date: 2026-09-22
description: Tìm hiểu cách tạo mã vạch PDF417 trong C#, thiết lập kích thước mã vạch
  và tạo các tệp hình ảnh mã vạch với các ví dụ mã rõ ràng, từng bước.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: vi
lastmod: 2026-09-22
og_description: Tạo mã vạch PDF417 trong C# nhanh chóng. Hướng dẫn này chỉ cách thiết
  lập kích thước mã vạch, bật chế độ gọn gàng và xuất ảnh PNG cho bất kỳ dự án .NET
  nào.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Tạo mã vạch PDF417 trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: Cách tạo mã vạch PDF417 và đặt kích thước trong C#
url: /vi/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 và đặt kích thước trong C#

Nếu bạn cần **tạo mã vạch PDF417** trong C#, hướng dẫn này sẽ chỉ cho bạn cách tạo mã vạch, kiểm soát kích thước của nó và lưu kết quả dưới dạng tệp ảnh. Dù bạn đang xây dựng hệ thống vé, nhãn logistics, hay chứng chỉ bảo mật, việc nắm vững định dạng PDF417 cho phép bạn mã hoá lượng lớn dữ liệu trong một hình ảnh gọn gàng.

Trong tutorial này bạn sẽ học:

* **Tạo mã vạch PDF417** bằng thư viện Aspose.BarCode (hoặc bất kỳ thư viện tương thích nào).  
* **Đặt kích thước mã vạch** bằng cách điều chỉnh X‑dimension và số cột.  
* Tạo **hình ảnh mã vạch trong C#** cho đầu ra PNG, JPEG hoặc BMP.  

Ví dụ sử dụng phiên bản cộng đồng miễn phí của Aspose.BarCode cho .NET, nhưng các khái niệm tương tự áp dụng cho các thư viện khác cung cấp các thuộc tính tương tự.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt.  
* Một IDE C# (Visual Studio, Visual Studio Code, Rider, v.v.).  
* Gói NuGet `Aspose.BarCode` (`dotnet add package Aspose.BarCode`).  

Không cần cấu hình bổ sung nào; thư viện hoạt động trên Windows, Linux và macOS.

## Bước 1: Tạo mã vạch PDF417 cơ bản và đặt kích thước

Bước đầu tiên là khởi tạo một `BarcodeGenerator` với enum `EncodeTypes.Pdf417` và cung cấp văn bản bạn muốn mã hoá. Sau đó điều chỉnh **X‑dimension** (độ rộng mô-đun) và số **cột** để kiểm soát kích thước tổng thể.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**Tại sao các cài đặt này quan trọng**

* `XDimension.Pixels` xác định độ rộng thanh hẹp nhất. Giá trị nhỏ hơn tạo mã vạch chặt hơn, trong khi giá trị lớn hơn tăng khả năng đọc trên máy quét độ phân giải thấp.  
* `Pdf417.Columns` ảnh hưởng đến tỷ lệ khung hình của mã vạch. Ít cột hơn làm mã vạch cao hơn; nhiều cột hơn làm nó phẳng hơn. Điều chỉnh số cột là cách chính để **đặt kích thước mã vạch** mà không thay đổi dữ liệu đã mã hoá.

Sau khi chạy mã, bạn sẽ thấy tệp `Pdf417Basic.png` trong thư mục đã chỉ định. Hình ảnh trông tương tự như ảnh chụp màn hình dưới đây:

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## Bước 2: Tạo mã vạch PDF417 compact (chế độ truncate) với cùng kích thước

Đôi khi bạn cần một mã vạch ngắn hơn cho không gian hạn chế. PDF417 cung cấp chế độ *truncate* (compact) loại bỏ mẫu dừng và giảm chiều cao tổng thể. Thuộc tính `Truncate` bật/tắt hành vi này.

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**Điều gì thay đổi khi `Truncate = true`?**

* Mã vạch ngắn hơn khoảng 15‑20 % theo chiều dọc, hữu ích cho nhãn nhỏ hoặc màn hình di động.  
* Dữ liệu vẫn được khôi phục đầy đủ; hầu hết máy quét hiện đại tự động hiểu chế độ truncate.

Kết quả `CompactPdf417.png` xuất hiện như một phiên bản mỏng hơn của mã vạch cơ bản.

## Bước 3: Tạo mã vạch Micro PDF417, điều chỉnh cột và lưu lại

Micro PDF417 là biến thể mật độ cao mới, được thiết kế cho không gian rất nhỏ (ví dụ: thẻ ID). Nó chỉ hỗ trợ 1‑4 cột và thư viện vẫn cung cấp thuộc tính `XDimension` để kiểm soát kích thước.

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Các điểm quan trọng cho Micro PDF417**

* Enum `EncodeTypes.MicroPdf417` tự động chọn biến thể micro.  
* Vì ký hiệu dày đặc hơn, bạn có thể cần máy in DPI cao (300 dpi trở lên) để giữ mã vạch đọc được.  
* Điều chỉnh số cột là nút duy nhất để thay đổi kích thước; thư viện vẫn tôn trọng `XDimension`.

## Cách đặt kích thước mã vạch cho các định dạng đầu ra khác nhau

Các ví dụ trên sử dụng PNG, nhưng phương thức `Save` cũng hoạt động với JPEG, BMP hoặc TIFF. Nếu bạn cần kích thước ảnh cụ thể (ví dụ: 300 × 150 px), kết hợp `XDimension` với `ResolutionX`/`ResolutionY`:

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

Tăng `ImageResolution` đồng thời thay đổi `XDimension` giúp duy trì chất lượng hình ảnh trên bản in độ phân giải cao.

## Những lỗi thường gặp và mẹo chuyên nghiệp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| Mã vạch xuất hiện mờ trên màn hình | DPI thấp kết hợp với `XDimension` nhỏ | Tăng `ImageResolution` và/hoặc `XDimension.Pixels` |
| Máy quét không thể đọc chế độ truncate | Firmware máy quét cũ không hỗ trợ | Sử dụng chế độ đầy đủ (không truncate) cho phần cứng cũ |
| Micro PDF417 không đọc được | In ở < 300 dpi hoặc độ tương phản không đủ | In trên giấy mờ ở 300 dpi hoặc cao hơn, đảm bảo nền tối |
| Tệp đầu ra bị hỏng | Thiếu quyền ghi vào thư mục đích | Kiểm tra `YOUR_DIRECTORY` tồn tại và có thể ghi |

**Mẹo chuyên nghiệp:** Luôn tạo mã vạch dưới dạng PNG khi bạn cần chất lượng không mất dữ liệu cho các xử lý tiếp theo (ví dụ: nhúng vào PDF). PNG giữ nguyên giá trị pixel, trong khi JPEG tạo ra các artefact nén có thể ảnh hưởng đến khả năng đọc mã vạch.

## Ví dụ đầy đủ, có thể chạy được

Dưới đây là một ứng dụng console hoàn chỉnh minh họa ba loại mã vạch trong một lần chạy. Sao chép mã vào dự án console .NET mới và thực thi.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**Kết quả mong đợi**

Chạy chương trình sẽ tạo ba tệp PNG trong thư mục `Barcodes`:

* `Pdf417Basic.png` – mã vạch PDF417 tiêu chuẩn với ba cột.  
* `CompactPdf417.png` – cùng dữ liệu ở chế độ truncate (compact), chiều cao ngắn hơn một chút.  
* `MicroPdf417.png` – biến thể Micro PDF417 mật độ cao với bốn cột.

Mở bất kỳ hình ảnh nào bằng trình xem ảnh; bạn sẽ thấy các dải đặc trưng stacked

## Bạn Nên Học Gì Tiếp Theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm mã mẫu đầy đủ với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách Tạo Mã Vạch – PDF417 Compact với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách Đặt Mức Lỗi trong Mã Vạch PDF417 – Hướng Dẫn Đầy Đủ](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Tạo Siêu Dữ Liệu Mã Vạch PDF417 trong C# – Hướng Dẫn Chi Tiết](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}