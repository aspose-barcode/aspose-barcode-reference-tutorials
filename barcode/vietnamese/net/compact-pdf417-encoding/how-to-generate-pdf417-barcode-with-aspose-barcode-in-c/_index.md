---
category: general
date: 2026-10-24
description: Tìm hiểu cách tạo mã vạch PDF417 bằng Aspose.BarCode trong C# với cài
  đặt compact và kiểm soát XDimension của mã vạch.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode
- compact PDF417
- barcode XDimension
- PDF417 columns
language: vi
lastmod: 2026-10-24
og_description: Tạo mã vạch PDF417 trong C# với Aspose.BarCode. Tham khảo hướng dẫn
  đầy đủ này để tạo hình ảnh PDF417 gọn nhẹ, kiểm soát XDimension và thiết lập số
  cột.
og_image_alt: Screenshot of generated PDF417 barcode using Aspose.BarCode
og_title: Tạo mã vạch PDF417 với Aspose.BarCode – C# từng bước
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  headline: How to generate PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to generate PDF417 barcode using Aspose.BarCode in C# with
    compact settings and barcode XDimension control.
  name: How to generate PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: 1. Changing the image format
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 2. Encoding large amounts of data
    text: 'PDF417 can store up to ~1.1 KB of text. When the payload exceeds the capacity
      of three columns, the library automatically adds rows. To keep the barcode compact,
      you can:'
  - name: 3. Using a license to remove the trial watermark
    text: '```csharp Aspose.BarCode.License license = new Aspose.BarCode.License();
      license.SetLicense("Aspose.BarCode.lic"); ```'
  - name: 4. Handling exceptions
    text: '```csharp try { generator.Save(outputPath, BarCodeImageFormat.Png); } catch
      (Exception ex) { Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
      } ```'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- PDF417
- C#
title: Cách tạo mã vạch PDF417 với Aspose.BarCode trong C#
url: /vi/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 với Aspose.BarCode trong C#

Nếu bạn cần **tạo mã vạch PDF417** trong một ứng dụng .NET, hướng dẫn này sẽ cho bạn một giải pháp hoàn chỉnh, sẵn sàng chạy. Bạn sẽ thấy cách Aspose.BarCode làm cho quá trình này trở nên đơn giản đồng thời cung cấp cho bạn khả năng kiểm soát chi tiết về **PDF417 compact**, **barcode XDimension**, và **các cột PDF417**.

Tạo mã vạch là một yêu cầu phổ biến cho các hệ thống quản lý tồn kho, nền tảng bán vé và quy trình làm việc với tài liệu. Khi kết thúc tutorial này, bạn sẽ có một chương trình C# tự chứa, tạo ra một hình ảnh PNG sắc nét của mã vạch PDF417, sẵn sàng nhúng vào bất kỳ giao diện người dùng nào hoặc in lên nhãn.

## Những gì bạn cần

- .NET 6.0 SDK hoặc phiên bản mới hơn (mã cũng hoạt động với .NET Framework 4.6+)
- Visual Studio 2022 hoặc bất kỳ trình chỉnh sửa C# nào bạn thích
- Giấy phép Aspose.BarCode for .NET hợp lệ (bản dùng thử miễn phí hoạt động cho việc phát triển)
- Kiến thức cơ bản về cú pháp C#

> **Pro tip:** Nếu bạn đang đánh giá Aspose.BarCode, tải bản dùng thử từ trang chính thức và thêm gói NuGet `Aspose.BarCode` vào dự án của bạn. Bản dùng thử sẽ thêm một watermark nhỏ vào hình ảnh được tạo, watermark này sẽ biến mất khi bạn áp dụng giấy phép.

## Bước 1: Cài đặt gói NuGet Aspose.BarCode

Mở terminal trong thư mục giải pháp của bạn và chạy:

```bash
dotnet add package Aspose.BarCode
```

Lệnh này tải về phiên bản ổn định mới nhất (tính đến tháng 10 2026, phiên bản 23.12). Thêm gói sẽ khôi phục namespace `Aspose.BarCode.Generation` mà bạn sẽ dùng để **tạo mã vạch PDF417** dưới dạng hình ảnh.

## Bước 2: Tạo một dự án console C# cơ bản

Nếu bạn chưa có dự án, tạo một dự án mới:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Mở `Program.cs`. Khung sườn đã chứa sẵn một phương thức `Main` nơi chúng ta sẽ đặt mã tạo mã vạch.

## Bước 3: Khởi tạo trình tạo mã vạch

Đầu tiên, nhập namespace cần thiết:

```csharp
using Aspose.BarCode.Generation;
```

Sau đó, trong `Main`, khởi tạo `BarcodeGenerator` với ký hiệu PDF417 và dữ liệu bạn muốn mã hoá:

```csharp
// Step 3: Initialize the generator for a PDF417 barcode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

Chuỗi này bao gồm các ký tự Unicode để minh họa Aspose.BarCode xử lý đúng đầu vào không phải ASCII. Nếu bạn chỉ cần ASCII, hãy thay thế văn bản bằng bất kỳ chuỗi đơn giản nào.

## Bước 4: Điều chỉnh barcode XDimension (kích thước mô-đun)

**barcode XDimension** xác định độ rộng của thanh nhỏ nhất (mô-đun). Đặt giá trị này bằng pixel cho phép bạn kiểm soát kích thước cuối cùng một cách chính xác:

```csharp
// Step 4: Set the module size – XDimension in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Giá trị `2` pixel tạo ra một hình ảnh gọn gàng mà không làm giảm độ tin cậy khi quét. Tăng giá trị để có mã vạch lớn hơn hoặc giảm để có bố cục rất dày đặc.

## Bước 5: Cấu hình tùy chọn PDF417 compact

Hai cài đặt riêng biệt của PDF417 ảnh hưởng mạnh mẽ đến kích thước hiển thị:

| Cài đặt | Ý nghĩa | Giá trị điển hình cho đầu ra compact |
|---------|---------|--------------------------------------|
| `Columns` | Số cột dữ liệu | `3` |
| `Truncate` (compact mode) | Bỏ vùng yên tĩnh bên phải và giảm số hàng | `true` |

Áp dụng chúng như sau:

```csharp
// Step 5: Use a small number of columns and enable compact mode
generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417
```

Sử dụng **cột PDF417** đặt thành `3` cùng với `Truncate = true` tạo ra một mã vạch *PDF417 compact* vừa vặn trên nhãn tiêu chuẩn mà vẫn có thể đọc được bởi hầu hết các máy quét.

## Bước 6: Lưu hình ảnh mã vạch

Cuối cùng, ghi mã vạch ra đĩa. Ví dụ này lưu dưới dạng PNG, nhưng Aspose.BarCode cũng hỗ trợ BMP, JPEG, GIF, TIFF và SVG:

```csharp
// Step 6: Save the barcode as a PNG file
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

Hằng số `BarCodeImageFormat.Png` thông báo cho thư viện tạo ra một PNG không mất dữ liệu, lý tưởng cho các bước xử lý hoặc in ấn tiếp theo.

## Mã nguồn đầy đủ, có thể chạy

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator for PDF417 with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size – barcode XDimension in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Configure compact PDF417 options
        generator.Parameters.Barcode.Pdf417.Columns = 3;      // PDF417 columns
        generator.Parameters.Barcode.Pdf417.Truncate = true; // compact PDF417

        // 4️⃣ Save as PNG
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "CompactPdf417.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

Chạy chương trình sẽ tạo ra file `CompactPdf417.png` trong thư mục gốc của dự án. Mở file bằng bất kỳ trình xem ảnh nào; bạn sẽ thấy một mã vạch PDF417 được nén chặt, mã hoá chuỗi *Åspóse.Barcóde©*.

![Ảnh chụp màn hình mã vạch PDF417 được tạo bằng Aspose.BarCode](placeholder-image.png "Mã vạch PDF417 đã tạo")

*Văn bản thay thế hình ảnh: Ảnh chụp màn hình mã vạch PDF417 được tạo bằng Aspose.BarCode* – văn bản thay thế này chứa từ khóa chính cho khả năng truy cập và SEO.

## Xác minh kết quả

1. Mở file PNG. Mã vạch nên gồm ba cột dữ liệu dọc với bố cục compact (không có vùng yên tĩnh thừa ở phía bên phải).
2. Quét hình ảnh bằng một ứng dụng quét mã vạch trên smartphone hỗ trợ PDF417. Văn bản giải mã phải khớp với chuỗi đầu vào ban đầu.
3. Nếu máy quét không thành công, thử tăng `XDimension.Pixels` lên `3` hoặc `4`. Các mô-đun lớn hơn cải thiện khả năng đọc trên thiết bị độ phân giải thấp.

## Các biến thể phổ biến và trường hợp đặc biệt

### 1. Thay đổi định dạng hình ảnh

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

SVG là định dạng vector, giữ cho mã vạch luôn sắc nét ở bất kỳ mức phóng đại nào—rất hữu ích cho các trang web.

### 2. Mã hoá lượng dữ liệu lớn

PDF417 có thể lưu trữ tới ~1.1 KB văn bản. Khi dữ liệu vượt quá khả năng của ba cột, thư viện sẽ tự động thêm hàng. Để giữ mã vạch gọn, bạn có thể:

- Giảm độ dài dữ liệu (ví dụ: sử dụng một định danh thay vì toàn bộ tin nhắn)
- Tăng số **cột PDF417** (ví dụ, `generator.Parameters.Barcode.Pdf417.Columns = 5;`)

### 3. Sử dụng giấy phép để loại bỏ watermark dùng thử

```csharp
Aspose.BarCode.License license = new Aspose.BarCode.License();
license.SetLicense("Aspose.BarCode.lic");
```

Đặt file giấy phép cạnh file thực thi. Sau khi cấp phép, hình ảnh được tạo sẽ không còn watermark.

### 4. Xử lý ngoại lệ

```csharp
try
{
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

Các lỗi thường gặp bao gồm quyền ghi không đủ hoặc định dạng hình ảnh không được hỗ trợ.

## Tại sao các cài đặt này quan trọng

- **barcode XDimension** – Kiểm soát độ dày trực quan của mỗi thanh. Quá nhỏ làm mã vạch không đọc được; quá lớn lãng phí không gian.
- **PDF417 columns** – Ít cột hơn tạo ra mã vạch hẹp hơn nhưng tăng số hàng.

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ, kèm giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch PDF417 với Aspose – Hướng dẫn đầy đủ](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Tạo mã vạch PDF417 với cài đặt compact trong C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-with-compact-settings-in-c/)
- [Cách lưu mã vạch và tạo PDF417 với Aspose trong C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}