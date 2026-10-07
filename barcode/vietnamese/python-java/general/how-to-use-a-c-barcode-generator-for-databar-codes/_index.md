---
category: general
date: 2026-09-23
description: Hướng dẫn tạo mã vạch bằng C# cho thấy cách tạo hình ảnh mã vạch với
  tỷ lệ khung hình tùy chỉnh bằng thư viện Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- DataBar barcode C#
- barcode aspect ratio
- Aspose.BarCode C#
- barcode image export
language: vi
lastmod: 2026-09-23
og_description: Hướng dẫn tạo mã vạch C# giúp bạn thực hiện cách tạo hình ảnh mã vạch,
  điều chỉnh tỷ lệ khung hình và xuất tệp PNG bằng Aspose.BarCode.
og_image_alt: Screenshot of a barcode created with a C# barcode generator
og_title: Tạo mã vạch chất lượng cao với trình tạo mã vạch C#
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  headline: How to use a C# barcode generator for DataBar codes
  type: TechArticle
- description: c# barcode generator tutorial shows how to generate barcode images
    with custom aspect ratios using the Aspose.BarCode library.
  name: How to use a C# barcode generator for DataBar codes
  steps:
  - name: Switching to another barcode type
    text: 'If you need a QR code, Code 128, or PDF417, replace the enum value in the
      constructor:'
  - name: Handling unsupported characters
    text: 'The `BarcodeGenerator` validates the input string against the selected
      symbology. Supplying an illegal character throws an `ArgumentException`. Wrap
      the creation in a try‑catch block to provide a friendly error message:'
  - name: Exporting to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the second argument
      of `Save` accordingly:'
  - name: High‑resolution output for printing
    text: 'When printing on high‑DPI printers, increase the X‑dimension and optionally
      set the `Resolution` property:'
  type: HowTo
tags:
- barcode
- c#
- Aspose
title: Cách sử dụng trình tạo mã vạch C# cho mã DataBar
url: /vi/python-java/general/how-to-use-a-c-barcode-generator-for-databar-codes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách sử dụng trình tạo mã vạch C# cho mã DataBar

Nếu bạn cần một **c# barcode generator** có thể tạo ra các ký hiệu DataBar stacked Omni‑Directional, hướng dẫn này cung cấp cho bạn một giải pháp hoàn chỉnh, sẵn sàng chạy. Bạn sẽ thấy cách tạo hình ảnh mã vạch, kiểm soát X‑dimension và thay đổi tỷ lệ khung hình mà không rời khỏi IDE.

Việc tạo mã vạch là một yêu cầu phổ biến cho các hệ thống quản lý tồn kho, nhãn vận chuyển và ứng dụng điểm bán hàng. Khi kết thúc tutorial này, bạn có thể tạo các tệp PNG với bất kỳ tỷ lệ khung hình nào bạn chọn, và sẽ hiểu cách điều chỉnh mã cho các loại mã vạch khác.

## Prerequisites

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ trình soạn thảo C# nào bạn thích)  
* Tham chiếu NuGet tới **Aspose.BarCode** – thư viện cung cấp lớp `BarcodeGenerator`  

Bạn không cần một thư viện đồ họa riêng; Aspose.BarCode xử lý việc mã hoá hình ảnh bên trong.

## Step 1: Install the Aspose.BarCode NuGet package

Mở terminal trong thư mục dự án của bạn và chạy:

```bash
dotnet add package Aspose.BarCode
```

Lệnh này sẽ thêm phiên bản ổn định mới nhất của thư viện vào tệp dự án, cho phép sử dụng lớp `BarcodeGenerator`.

## Step 2: Define the output folder

Chọn một thư mục nơi các tệp PNG được tạo sẽ được lưu. Sử dụng đường dẫn tuyệt đối hoặc tương đối đều hoạt động tương tự, nhưng đường dẫn tương đối giúp dự án di động hơn.

```csharp
// Define the output folder (relative to the project root)
string outputFolder = "GeneratedBarcodes/";
Directory.CreateDirectory(outputFolder); // Ensure the folder exists
```

Tạo thư mục bằng chương trình ngăn ngừa lỗi thời gian chạy nếu thư mục chưa tồn tại.

## Step 3: Instantiate the C# barcode generator with sample data

Constructor của `BarcodeGenerator` yêu cầu hai đối số: loại mã vạch và chuỗi dữ liệu. Đối với ký hiệu DataBar stacked Omni‑Directional, bạn sử dụng `EncodeTypes.DatabarStackedOmniDirectional`.

```csharp
// Create a barcode generator for a DataBar stacked Omni‑Directional code
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

Chuỗi dữ liệu tuân theo định dạng GS1 Application Identifier. Enum `EncodeTypes` chứa hơn 150 tiêu chuẩn mã vạch; bạn có thể chuyển sang loại khác bằng cách thay đổi giá trị enum.

## Step 4: Set the X‑dimension (pixel size) for the barcode

X‑dimension kiểm soát độ rộng của thanh hẹp nhất. Giá trị pixel là 2 sẽ cho ra hình ảnh sắc nét, độ phân giải cao, phù hợp với hầu hết các màn hình.

```csharp
// Set the X‑dimension to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Việc điều chỉnh X‑dimension là tùy chọn, nhưng nó cho bạn khả năng kiểm soát chi tiết mật độ hình ảnh của mã vạch.

## Step 5: Generate a barcode with an aspect ratio of 15 and save it as PNG

Thuộc tính `AspectRatio` thuộc đối tượng con `DataBar`. Thay đổi giá trị này sẽ kéo dài hoặc nén mã vạch theo chiều dọc trong khi vẫn giữ nguyên dữ liệu đã mã hoá.

```csharp
// Set aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Phương thức `Save` ghi mã vạch vào đường dẫn tệp đã chỉ định. Enum `BarCodeImageFormat.Png` đảm bảo nén không mất dữ liệu.

![c# barcode generator output example](generated_barcode_example.png)

*Image: barcode generated with an aspect ratio of 15.*

## Step 6: Change the aspect ratio to 30 and generate a second image

Việc tái sử dụng cùng một thể hiện `BarcodeGenerator` tránh việc cấp phát đối tượng mới. Chỉ cần cập nhật `AspectRatio` và gọi lại `Save`.

```csharp
// Update aspect ratio to 30 and save a second image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save($"{outputFolder}DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

Bây giờ bạn có hai tệp PNG chỉ khác nhau ở mức độ phóng đại theo chiều dọc. Kỹ thuật này hữu ích khi bạn cần cùng một dữ liệu được hiển thị cho các kích thước nhãn khác nhau.

## Common variations and edge cases

### Switching to another barcode type

Nếu bạn cần một QR code, Code 128, hoặc PDF417, hãy thay thế giá trị enum trong constructor:

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(
    EncodeTypes.QR, "https://example.com");
```

Tất cả các bước cấu hình khác (X‑dimension, lưu) vẫn giữ nguyên.

### Handling unsupported characters

`BarcodeGenerator` sẽ kiểm tra chuỗi đầu vào dựa trên ký hiệu đã chọn. Việc cung cấp ký tự không hợp lệ sẽ ném ra `ArgumentException`. Bao bọc việc tạo trong khối try‑catch để đưa ra thông báo lỗi thân thiện:

```csharp
try
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for the selected barcode type: {ex.Message}");
}
```

### Exporting to other image formats

Aspose.BarCode hỗ trợ BMP, JPEG, TIFF và SVG. Thay đổi đối số thứ hai của `Save` cho phù hợp:

```csharp
barcodeGenerator.Save($"{outputFolder}Databar.svg", BarCodeImageFormat.Svg);
```

### High‑resolution output for printing

Khi in trên máy in DPI cao, tăng X‑dimension và tùy chọn thiết lập thuộc tính `Resolution`:

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.ImageResolution.Dpi = 300;
```

Các thiết lập này tạo ra các tệp lớn hơn nhưng vẫn giữ được các cạnh sắc nét trên vật liệu in.

## Expected output

Chạy chương trình đầy đủ sẽ tạo ra các tệp sau trong thư mục `GeneratedBarcodes/`:

* `DatabarAspectRatio15.png` – mã DataBar có chiều cao tiêu chuẩn  
* `DatabarAspectRatio30.png` – phiên bản kéo dài theo chiều dọc  

Cả hai hình ảnh đều chứa cùng một dữ liệu GS1 đã mã hoá, và bạn có thể xác minh chúng bằng bất kỳ ứng dụng quét mã vạch nào.

## Full source code

Sao chép đoạn mã dưới đây vào một dự án console mới (`dotnet new console`) và chạy. Chương trình sẽ in thông báo trạng thái ra console và ghi các tệp PNG vào đĩa.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Define the output folder
        string outputFolder = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputFolder);

        // Step 3: Create a C# barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Step 4: Set common barcode properties (pixel size of X‑dimension)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 5: Generate a barcode with aspect ratio 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputFolder, "DatabarAspectRatio15.png");
        barcodeGenerator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Step 6: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputFolder, "DatabarAspectRatio30.png");
        barcodeGenerator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

Chạy chương trình sẽ tạo ra đầu ra console tương tự như:

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

## Conclusion

Bạn đã có một **c# barcode generator** có thể tạo các ký hiệu DataBar stacked Omni‑Directional, điều chỉnh X‑dimension và xuất tệp PNG với tỷ lệ khung hình tùy chỉnh. Mẫu tương tự áp dụng cho bất kỳ ký hiệu mã vạch nào khác được Aspose.BarCode hỗ trợ, giúp bạn dễ dàng tích hợp việc tạo mã vạch vào các giải pháp quản lý tồn kho, vận chuyển hoặc điểm bán hàng.

Nếu muốn khám phá sâu hơn, hãy thử:

* Tạo QR code hoặc ký hiệu PDF417 (`how to generate barcode` cho ứng dụng di động)  
* Xuất ra SVG cho đồ họa web có thể mở rộng  
* Nhúng các hình ảnh đã tạo trực tiếp vào hóa đơn PDF bằng Aspose.PDF  

Thử nghiệm với các giá trị `AspectRatio`, kích thước X‑dimension và định dạng đầu ra khác nhau để phù hợp chính xác với nhu cầu của bạn.

## What Should You Learn Next?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm mã nguồn đầy đủ và các giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}