---
category: general
date: 2026-10-21
description: Tạo hình ảnh mã vạch databar expanded stacked bằng C# sử dụng BarcodeGenerator.
  Thực hiện theo hướng dẫn từng bước này để tạo hình ảnh mã vạch, tùy chỉnh hàng và
  cột, và xuất file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: vi
lastmod: 2026-10-21
og_description: Tạo mã vạch databar mở rộng xếp chồng trong C# với hướng dẫn này.
  Tìm hiểu cách sử dụng BarcodeGenerator, thiết lập hàng và cột, và lưu ảnh PNG.
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: Tạo mã vạch Databar Expanded Stacked bằng C# – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách tạo mã vạch Databar Expanded Stacked bằng C#
url: /vi/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch databar expanded stacked trong C#

Nếu bạn cần tạo một mã vạch **databar expanded stacked** trong C#, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Ký hiệu databar expanded stacked lý tưởng cho việc mã hoá lượng lớn dữ liệu trong một dạng gọn gàng, và bạn có thể tạo hình ảnh chỉ với vài dòng mã. Bạn cũng sẽ học cách **tạo file hình ảnh mã vạch** ở các định dạng khác nhau và tùy chỉnh hàng hoặc cột để phù hợp với môi trường quét của bạn.

Hướng dẫn này bao gồm mọi thứ bạn cần để bắt đầu sản xuất mã vạch databar: cài đặt thư viện cần thiết, chuẩn bị thư mục đầu ra, tạo mã vạch với hàng hoặc cột tùy chỉnh, và lưu kết quả dưới dạng file PNG. Khi hoàn thành, bạn sẽ có thể **tạo hình ảnh mã vạch databar** một cách lập trình và điều chỉnh mã cho các định dạng ảnh khác hoặc các kịch bản runtime.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc phiên bản mới hơn (mã cũng hoạt động với .NET Core 3.1 và .NET Framework 4.7+)
* Môi trường phát triển như Visual Studio 2022, Visual Studio Code hoặc Rider
* Kết nối Internet để cài đặt gói NuGet **Barcode Generator C#** (Aspose.BarCode for .NET)

> **Mẹo:** Nếu bạn đang sử dụng pipeline CI/CD, hãy thêm tham chiếu gói NuGet vào file dự án của bạn để quá trình build có thể tái tạo.

## Cài đặt thư viện Barcode Generator C# library

Ví dụ sử dụng thư viện Aspose.BarCode, cung cấp lớp `BarcodeGenerator` và enumeration `EncodeTypes.DatabarExpandedStacked`.

```bash
dotnet add package Aspose.BarCode
```

Lệnh này sẽ thêm phiên bản ổn định mới nhất vào dự án của bạn. Sau khi cài đặt, bạn có thể nhập namespace trong các file C#:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## Chuẩn bị thư mục đầu ra

Một đường dẫn file đáng tin cậy ngăn ngừa lỗi runtime khi thư viện cố gắng ghi ảnh. Đoạn mã sau sẽ tạo thư mục nếu nó chưa tồn tại:

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **Tại sao điều này quan trọng:** Cố gắng lưu vào thư mục không tồn tại sẽ gây ra `IOException`. Tạo thư mục trước giúp mã ổn định hơn cho cả môi trường phát triển cục bộ và sản xuất.

## Tạo hình ảnh mã vạch databar expanded stacked

### Tạo mã vạch cơ bản

Cách đơn giản nhất để tạo một hình ảnh **databar expanded stacked** là khởi tạo `BarcodeGenerator` với giá trị `EncodeTypes` mong muốn và payload dạng văn bản thuần.

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

Chạy đoạn mã sẽ tạo ra file `DatabarBasic.png` trong thư mục *Barcodes*. Hình ảnh chứa một ký hiệu databar expanded stacked tiêu chuẩn với bố cục mặc định (4 cột × 4 hàng).

### Tùy chỉnh cột – tạo mã vạch databar với 4 cột

Bạn có thể kiểm soát số cột bằng thuộc tính `Parameters.Barcode.DataBar.Columns`. Ví dụ sau tạo mã vạch với **4 cột** trong khi giữ số hàng mặc định.

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

File kết quả, **DatabarCols4.png**, trông như sau:

![Mã vạch databar expanded stacked với 4 cột](databar_cols4.png "Mã vạch databar expanded stacked với 4 cột – tạo bằng C#")

*Văn bản thay thế hình ảnh (og_image_alt):* **Mẫu hình ảnh mã vạch databar expanded stacked được tạo bằng C#** – đáp ứng yêu cầu SEO cho văn bản thay thế hình ảnh.

### Tùy chỉnh hàng – tạo mã vạch databar với 3 hàng

Tương tự, bạn có thể điều chỉnh số hàng qua `Parameters.Barcode.DataBar.Rows`. Đoạn mã dưới đây tạo mã vạch với **3 hàng** và số cột mặc định (4).

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

File **DatabarRows3.png** chứa một ký hiệu databar expanded stacked hơi ngắn hơn theo chiều dọc, hữu ích cho các nhãn có không gian hạn chế.

### Xuất sang các định dạng khác

Nếu bạn cần một loại ảnh khác (ví dụ: JPEG, BMP, hoặc SVG), thay thế `BarCodeImageFormat.Png` bằng giá trị enum phù hợp:

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

Thư viện cũng hỗ trợ các định dạng vector như SVG, rất lý tưởng cho việc in ấn độ phân giải cao.

## Các kịch bản nâng cao

### Lưu vào memory stream

Đôi khi bạn muốn nhúng mã vạch trực tiếp vào phản hồi web hoặc PDF mà không cần ghi vào hệ thống file. Sử dụng `MemoryStream`:

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### Xử lý đầu vào không hợp lệ

`BarcodeGenerator` sẽ kiểm tra payload dựa trên ký hiệu đã chọn. Nếu dữ liệu chứa ký tự bị cấm, sẽ ném ra `ArgumentException`. Bao quanh mã tạo trong khối try‑catch để cung cấp thông báo lỗi thân thiện:

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### Thay đổi kích thước hình ảnh mã vạch

Bạn có thể thay đổi kích thước ảnh mà không làm thay đổi dữ liệu đã mã hoá bằng cách đặt `Parameters.Image.Width` và `Parameters.Image.Height`:

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

Việc thay đổi kích thước hữu ích khi mã vạch phải đáp ứng yêu cầu DPI cụ thể cho máy quét.

## Ví dụ hoàn chỉnh

Dưới đây là một ứng dụng console đầy đủ, sẵn sàng chạy, minh họa tất cả các bước đã thảo luận:

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**Kết quả mong đợi**


## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao quát các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ code hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách đặt cột cho mã vạch Databar Expanded Stacked – hướng dẫn C# đầy đủ](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [Cách xây dựng ví dụ trình tạo mã vạch trong C# với DataBar Expanded Stacked](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [Hướng dẫn mã vạch databar expanded stacked – cách tạo và định kích thước trong C#](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}