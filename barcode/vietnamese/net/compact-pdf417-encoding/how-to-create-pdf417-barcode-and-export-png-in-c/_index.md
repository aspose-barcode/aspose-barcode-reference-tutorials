---
category: general
date: 2026-09-19
description: Tạo mã vạch PDF417 trong C# và tìm hiểu cách tạo hình ảnh mã vạch, thiết
  lập kích thước mã vạch và lưu dưới dạng PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode image
- how to set barcode dimensions
- how to create barcode png
language: vi
lastmod: 2026-09-19
og_description: Tạo mã vạch PDF417 bằng C# và khám phá cách tạo hình ảnh mã vạch,
  thiết lập kích thước mã vạch, và lưu nó dưới dạng tệp PNG.
og_image_alt: Sample PDF417 barcode generated with C# showing custom dimensions saved
  as PNG
og_title: Tạo mã vạch PDF417 và xuất PNG trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: Create PDF417 barcode in C# and learn how to generate barcode image,
    set barcode dimensions, and save as PNG.
  headline: How to create PDF417 barcode and export PNG in C#
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- image generation
title: Cách tạo mã vạch PDF417 và xuất PNG trong C#
url: /vi/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 và xuất PNG trong C#

Nếu bạn cần **tạo mã vạch PDF417** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách tạo hình ảnh mã vạch, điều chỉnh kích thước và lưu nó dưới dạng tệp PNG. Bạn sẽ thấy một ví dụ hoàn chỉnh, có thể chạy được sử dụng thư viện Aspose.BarCode, để bạn có thể sao chép mã trực tiếp vào dự án của mình.

Việc tạo hình ảnh mã vạch là một yêu cầu phổ biến cho các hệ thống bán vé, theo dõi tồn kho và vé lên máy bay di động. Khi kết thúc hướng dẫn này, bạn sẽ hiểu **cách tạo hình ảnh mã vạch**, **cách đặt kích thước mã vạch**, và **cách tạo tệp PNG cho mã vạch** đáp ứng tiêu chuẩn chất lượng hình ảnh của bạn.

## Yêu cầu trước

* .NET 6.0 SDK hoặc phiên bản mới hơn (mã cũng hoạt động với .NET Framework 4.7+).
* Môi trường phát triển như Visual Studio 2022 hoặc VS Code.
* Giấy phép hợp lệ cho thư viện **Aspose.BarCode for .NET** (bản dùng thử miễn phí hoạt động cho ví dụ này).
* Kiến thức cơ bản về cú pháp C#.

Install the NuGet package with the following command:

```bash
dotnet add package Aspose.BarCode
```

## Bước 1: Thiết lập dự án và nhập không gian tên

Tạo một ứng dụng console mới hoặc thêm mã vào dự án hiện có. Nhập các không gian tên cần thiết ở đầu tệp:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Các không gian tên này cho phép bạn truy cập vào lớp `BarcodeGenerator` và kiểu liệt kê `EncodeTypes`.

## Bước 2: Cách tạo mã vạch PDF417 – cấu hình bộ tạo cơ bản

Hoạt động đầu tiên là tạo một thể hiện của `BarcodeGenerator` với kiểu mã hoá `Pdf417` và văn bản bạn muốn mã hoá. Đối tượng này đại diện cho mã vạch mà bạn sẽ render sau này.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");
```

*​Tại sao điều này quan trọng*: `EncodeTypes.Pdf417` thông báo cho thư viện sử dụng ký hiệu PDF417, là một mã vạch tuyến tính xếp chồng có khả năng lưu trữ lượng dữ liệu lớn. Tham số thứ hai (“Sample”) là dữ liệu sẽ xuất hiện khi mã vạch được quét.

## Bước 3: Cách đặt kích thước mã vạch – tinh chỉnh mật độ và bố cục

Mã vạch PDF417 bao gồm các hàng và cột của các mô-đun. Điều chỉnh kích thước X (độ rộng mô-đun) và số hàng/cột cho phép bạn kiểm soát mật độ hình ảnh và kích thước tổng thể của ảnh.

```csharp
// Step 3: Set the module (X) dimension in pixels – controls the barcode's density
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Define the barcode layout – number of columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;   // up to 30 columns
generator.Parameters.Barcode.Pdf417.Rows    = 9;   // up to 90 rows
```

*​Tại sao điều này quan trọng*:  
* **X‑dimension** xác định độ rộng của mỗi ô vuông nhỏ (mô-đun). Giá trị nhỏ hơn tạo ra mã vạch gọn hơn nhưng có thể khó quét đối với máy quét độ phân giải thấp.  
* **Columns** và **Rows** ảnh hưởng đến dung lượng dữ liệu và hình dạng vật lý. Tăng số cột làm mã vạch rộng hơn; tăng số hàng làm nó cao hơn. Bạn có thể thử nghiệm các giá trị lên tới giới hạn được ghi trong chú thích.

**Mẹo chuyên nghiệp**: Nếu mã vạch trông quá dày trên màn hình DPI cao, tăng `XDimension.Pixels` lên 3 hoặc 4. Ngược lại, đối với nhãn nhỏ, bạn có thể đặt nó thành 1 pixel và giảm số cột.

## Bước 4: Cách tạo hình ảnh mã vạch – render vào bitmap trong bộ nhớ

Sau khi cấu hình bộ tạo, bạn có thể render mã vạch thành một đối tượng hình ảnh. Bước này là tùy chọn nếu bạn chỉ cần lưu tệp trực tiếp, nhưng việc lấy bitmap cho phép bạn thực hiện các xử lý tiếp theo (ví dụ: thêm logo hoặc vẽ viền).

```csharp
// Step 4: Render the barcode to a bitmap (optional but useful for further manipulation)
using var barcodeImage = generator.GenerateBarCodeImage();
```

`GenerateBarCodeImage()` trả về một `System.Drawing.Image` mà bạn có thể thao tác bằng GDI+ nếu muốn.

## Bước 5: Cách tạo PNG cho mã vạch – lưu tệp ảnh cuối cùng

Cuối cùng, ghi ảnh ra đĩa ở định dạng PNG. PNG giữ nguyên chất lượng không mất dữ liệu, rất phù hợp cho các ứng dụng quét mã.

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*​Tại sao điều này quan trọng*: Phương thức `Save` xử lý việc mã hoá và I/O tệp cho bạn. Sử dụng `BarCodeImageFormat.Png` đảm bảo đầu ra là ảnh di động, không mất dữ liệu, hoạt động trên mọi trình duyệt và thiết bị di động.

### Ví dụ đầy đủ có thể chạy

Dưới đây là chương trình hoàn chỉnh mà bạn có thể dán vào `Program.cs` và chạy. Thay thế `YOUR_DIRECTORY` bằng thư mục tồn tại trên máy của bạn.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create the generator with PDF417 symbology
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample");

        // 2. Adjust dimensions for desired visual density
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4; // up to 30
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // up to 90

        // 3. (Optional) Render to a bitmap if you need further processing
        // using var image = generator.GenerateBarCodeImage();

        // 4. Save as PNG
        string outputPath = @"YOUR_DIRECTORY\Pdf417Custom.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode created and saved to: {outputPath}");
    }
}
```

Chạy chương trình sẽ tạo ra một tệp PNG trông như sau:

![Ví dụ mã vạch PDF417 đã tạo](https://example.com/placeholder-image.png "Mã vạch PDF417 được tạo với kích thước tùy chỉnh và lưu dưới dạng PNG")

*Văn bản thay thế*: **Mã vạch PDF417 mẫu được tạo bằng C# với kích thước tùy chỉnh và lưu dưới dạng PNG** – điều này đáp ứng yêu cầu **tạo mã vạch PDF417** cho khả năng truy cập hình ảnh.

## Các biến thể phổ biến và trường hợp đặc biệt

| Tình huống | Điều chỉnh đề xuất |
|-----------|------------------------|
| **Nhãn rất nhỏ** (ví dụ: 1 cm × 2 cm) | Đặt `XDimension.Pixels = 1` và giảm `Columns` xuống 2‑3. Kiểm tra khả năng đọc của máy quét. |
| **In độ phân giải cao** (300 dpi hoặc hơn) | Tăng `XDimension.Pixels` lên 3‑4 và tùy chọn tăng `Rows` để có dung lượng dữ liệu lớn hơn. |
| **Cần định dạng ảnh khác** (JPEG, BMP) | Thay đổi `BarCodeImageFormat.Png` thành `BarCodeImageFormat.Jpeg` hoặc `BarCodeImageFormat.Bmp`. |
| **Nhúng vào PDF** | Sử dụng `generator.Save("output.pdf", BarCodeImageFormat.Pdf)` thay vì PNG. |
| **Dữ liệu động** (nhập từ người dùng) | Thay thế chuỗi tĩnh `"Sample"` bằng một biến, ví dụ `userInput`. Đảm bảo độ dài văn bản không vượt quá giới hạn PDF417 (≈ 1 800 ký tự). |

## Danh sách kiểm tra khắc phục sự cố

* **Hình ảnh trống** – Kiểm tra thư mục đầu ra tồn tại và ứng dụng có quyền ghi.  
* **Mã vạch không thể quét** – Tăng `XDimension.Pixels` hoặc thêm nhiều cột/hàng hơn; nền có độ tương phản thấp cũng có thể gây lỗi.  
* **Kích thước không mong muốn** – Kiểm tra lại giá trị `Columns` và `Rows`; thư viện tuân thủ các giới hạn tối đa được ghi trong chú thích.  

## Các bước tiếp theo

Bây giờ bạn đã có thể **tạo mã vạch PDF417**, hãy cân nhắc khám phá các chủ đề liên quan sau:

* **Cách tạo hình ảnh mã vạch** ở các định dạng khác như SVG cho đồ họa web‑scalable.  
* **Cách đặt kích thước mã vạch** cho các ký hiệu QR và DataMatrix.  
* **Cách tạo PNG cho mã vạch** với màu tùy chỉnh hoặc logo nhúng bằng `System.Drawing`.  

Các mở rộng này cho phép bạn xây dựng một dịch vụ tạo mã vạch đầy đủ tính năng, có thể phục vụ các ứng dụng di động, cổng thông tin web và tiện ích máy tính để bàn.

---

*Bạn đã học cách tạo mã vạch PDF417, tùy chỉnh kích thước, render hình ảnh mã vạch và lưu nó dưới dạng tệp PNG bằng C#. Áp dụng các mẫu được trình bày ở đây cho các loại mã vạch và định dạng ảnh khác để mở rộng khả năng tự động hoá của bạn.*

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được minh họa trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh, hoạt động với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo hình ảnh mã vạch PDF417 trong C# với Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [Cách tạo mã vạch PDF417 với Aspose – Hướng dẫn chi tiết từng bước](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Cách lưu mã vạch trong C# – Tạo mã vạch PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}