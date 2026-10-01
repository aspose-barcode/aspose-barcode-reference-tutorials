---
category: general
date: 2026-09-13
description: Học cách tạo hình ảnh mã vạch PDF417 trong C# bằng BarcodeGenerator và
  các tùy chọn Macro PDF417. Mã từng bước, mẹo và ví dụ đầy đủ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: vi
lastmod: 2026-09-13
og_description: Tạo hình ảnh mã vạch PDF417 trong C# bằng BarcodeGenerator. Thực hiện
  theo hướng dẫn chi tiết này để cấu hình các tùy chọn Macro PDF417 và lưu mã vạch
  dưới dạng PNG.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Tạo hình ảnh mã vạch PDF417 trong C# – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: Cách tạo hình ảnh mã vạch PDF417 trong C# với các tùy chọn Macro PDF417
url: /vi/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo hình ảnh mã vạch PDF417 trong C# với các tùy chọn Macro PDF417

Nếu bạn cần **tạo hình ảnh mã vạch PDF417** trong C#, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chính xác bằng cách sử dụng **lớp BarcodeGenerator**. Dù bạn đang xây dựng hệ thống theo dõi tài liệu hay mã hoá các tệp lớn, các hướng dẫn từng bước dưới đây sẽ bao gồm mọi thứ từ việc thiết lập các tùy chọn Macro PDF417 đến việc lưu PNG cuối cùng.

Việc tạo mã vạch trở nên đơn giản ngay khi bạn hiểu các tham số chính. Trong tutorial này bạn sẽ học cách:

* Khởi tạo một `BarcodeGenerator` cho **Macro PDF417**.  
* Điều chỉnh kích thước mô-đun mã vạch (`XDimension`).  
* Cấu hình các thiết lập riêng cho từng segment như file ID, segment ID và checksum.  
* Lưu kết quả dưới dạng **định dạng hình ảnh mã vạch** (PNG) có thể hiển thị trong bất kỳ UI nào.

Điều kiện tiên quyết duy nhất là môi trường phát triển .NET (Visual Studio 2022 hoặc mới hơn) và gói NuGet Aspose.BarCode for .NET, cung cấp API `BarcodeGenerator` được sử dụng trong các ví dụ.

---

## Cách tạo hình ảnh mã vạch PDF417 trong C# – tổng quan

Việc tạo hình ảnh mã vạch PDF417 bao gồm bốn bước logic:

1. **Tạo generator** – khởi tạo `BarcodeGenerator` với `EncodeTypes.MacroPdf417` và dữ liệu bạn muốn mã hoá.  
2. **Xác định kích thước mô-đun** – đặt `XDimension.Pixels` để kiểm soát độ rộng thực tế của mỗi phần tử mã vạch.  
3. **Cấu hình các tùy chọn Macro PDF417** – chỉ định số cột, định danh tệp, số segment và checksum tùy chọn.  
4. **Lưu mã vạch** – ghi hình ảnh đã tạo ra đĩa bằng một **định dạng hình ảnh mã vạch** được hỗ trợ như PNG.

Mỗi bước được giải thích chi tiết dưới đây, kèm theo mã C# đầy đủ, có thể chạy được.

---

## Bước 1: Khởi tạo BarcodeGenerator cho Macro PDF417

Dòng đầu tiên tạo một đối tượng `BarcodeGenerator` biết rằng nó phải tạo ra một mã vạch **Macro PDF417**. Hàm khởi tạo nhận hai đối số: kiểu mã hoá và chuỗi dữ liệu thô.

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**Tại sao điều này quan trọng:**  
`EncodeTypes.MacroPdf417` thông báo cho thư viện xử lý mã vạch như một container đa‑segment, rất cần thiết khi bạn phải chia một tệp lớn thành nhiều ký hiệu. Đối tượng `BarcodeGenerator` có thể được giải phóng, vì vậy khối `using` đảm bảo tất cả tài nguyên không quản lý được giải phóng sau khi hình ảnh được lưu.

---

## Bước 2: Đặt kích thước mô-đun mã vạch (XDimension)

`XDimension` kiểm soát độ rộng tính bằng pixel của một mô-đun mã vạch duy nhất (vạch đen hoặc trắng nhỏ nhất). Giá trị **2 pixel** tạo ra một hình ảnh gọn gàng nhưng vẫn dễ đọc.

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Mẹo thực tế:**  
Nếu máy in mục tiêu của bạn có DPI thấp, tăng số pixel (ví dụ, `3` hoặc `4`) để tránh bị nhòe. Ngược lại, đối với hiển thị trên màn hình, bạn có thể giữ giá trị thấp để giảm kích thước tệp.

---

## Bước 3: Cấu hình các tùy chọn riêng cho Macro PDF417

Macro PDF417 thêm siêu dữ liệu cho phép máy quét tái tạo lại tệp gốc từ nhiều segment mã vạch. Các tùy chọn phổ biến nhất là:

| Thuộc tính | Ý nghĩa |
|------------|----------|
| `Columns` | Số cột trong mỗi ký hiệu (ảnh hưởng đến độ rộng). |
| `MacroPdf417FileID` | Định danh duy nhất cho toàn bộ tệp. |
| `MacroPdf417SegmentID` | Chỉ số của segment hiện tại (bắt đầu từ 1). |
| `MacroPdf417SegmentsCount` | Tổng số segment tạo nên tệp. |
| `MacroPdf417FileName` | Tên tệp gốc (tùy chọn, dùng để hiển thị). |
| `MacroPdf417Checksum` | Checksum 16‑bit tùy chọn để xác minh tính toàn vẹn. |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**Tại sao các thiết lập này quan trọng:**  
- **Columns** ảnh hưởng đến khả năng đọc và kích thước tổng thể của hình ảnh.  
- **FileID** phải giống nhau trên mọi segment để bộ giải mã biết chúng thuộc cùng một tệp.  
- **SegmentID** và **SegmentsCount** giúp máy quét sắp xếp các phần đúng thứ tự.  
- **FileName** và **Checksum** là tùy chọn nhưng cải thiện trải nghiệm người dùng và độ tin cậy dữ liệu.

**Trường hợp đặc biệt:** Nếu bạn tạo hơn 999 segment, trường `SegmentID` sẽ tràn; hãy chia dữ liệu thành nhiều tệp thay vì một tệp duy nhất.

---

## Bước 4: Lưu mã vạch đã tạo dưới dạng ảnh PNG

Bước cuối cùng ghi mã vạch ra đĩa. `BarCodeImageFormat.Png` tạo ra một hình ảnh không mất dữ liệu, hoạt động tốt trên web, desktop và các nền tảng di động.

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**Định dạng thay thế:**  
Bạn có thể thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp` hoặc `Gif` nếu hệ thống downstream yêu cầu định dạng cụ thể. Hãy nhớ rằng JPEG tạo ra các artefact nén có thể làm giảm độ tin cậy khi quét.

**Kết quả mong đợi:**  
Tệp `MacroPdf417.png` sẽ chứa một mã vạch PDF417 đa‑segment với độ tương phản cao. Khi mở, nó sẽ trông tương tự như minh họa bên dưới.

![Ví dụ tạo hình ảnh mã vạch PDF417](image.png){: .align-center alt="Ví dụ tạo hình ảnh mã vạch PDF417 được tạo bằng mã C#"}

---

## Mã nguồn đầy đủ – sẵn sàng sao chép và chạy

Dưới đây là chương trình hoàn chỉnh, tự chứa. Nó bao gồm các chỉ thị `using` cần thiết, phương thức `Main`, và các chú thích giải thích từng dòng không hiển nhiên.

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**Chạy chương trình:**  

1. Tạo một dự án console .NET 6 (hoặc mới hơn).  
2. Thêm gói NuGet Aspose.BarCode (`dotnet add package Aspose.BarCode`).  
3. Thay thế file `Program.cs` được tạo sẵn bằng mã ở trên.  
4. Điều chỉnh `outputPath` tới thư mục bạn có quyền ghi.  
5. Biên dịch và chạy – console sẽ xác nhận vị trí của hình ảnh.

---

## Câu hỏi thường gặp & khắc phục sự cố

| Câu hỏi | Trả lời |
|----------|--------|
| *Nếu mã vạch quá rộng so với nhãn của tôi thì sao?* | Giảm `Columns` hoặc tăng `XDimension.Pixels` để cân bằng độ rộng và khả năng đọc. |
| *Có cần phải đặt checksum không?* | Checksum là tùy chọn |

## Bạn Nên Học Gì Tiếp Theo?


Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh, kèm theo giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo mã vạch PDF417 trong C# – Hướng dẫn chi tiết từng bước](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [Tạo siêu dữ liệu mã vạch PDF417 trong C# – Hướng dẫn chi tiết từng bước](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [Tạo mã vạch kèm văn bản – Hướng dẫn đầy đủ Macro PDF417](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}