---
category: general
date: 2026-11-27
description: Tìm hiểu cách tạo mã vạch PDF417 trong C# bằng Aspose.BarCode. Điều chỉnh
  kích thước, đặt số cột và lưu dưới dạng PNG chỉ trong vài dòng mã.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- Aspose.BarCode C#
- PDF417 barcode dimensions
- barcode image PNG
- BarcodeGenerator usage
language: vi
lastmod: 2026-11-27
og_description: Tạo mã vạch PDF417 trong C# ngay lập tức. Hướng dẫn này chỉ cách cấu
  hình kích thước, số cột và lưu kết quả dưới dạng ảnh PNG.
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: Tạo mã vạch PDF417 trong C# – hướng dẫn nhanh với Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  headline: How to generate PDF417 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using Aspose.BarCode. Adjust
    dimensions, set column count, and save as PNG in a few lines of code.
  name: How to generate PDF417 barcode in C# with Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **BarcodeGenerator** – the core class that creates a barcode image. Passing
      `EncodeTypes.Pdf417` selects the PDF417 symbology. * **XDimension.Pixels** –
      determines the smallest bar width. Smaller values shrink the image; larger values
      improve readability on low‑resolution scanners. * **Pdf417.Colu'
  - name: Changing the encoded data
    text: 'Replace the second argument of `BarcodeGenerator` with any UTF‑8 string,
      e.g.:'
  - name: Adjusting image size without losing quality
    text: 'If you need a larger image for printing, increase `XDimension.Pixels`:'
  - name: Handling very long inputs
    text: 'PDF417 can encode up to 1 850 characters. For extremely long strings, you
      may want to increase the column count:'
  - name: Saving in other formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG. Change the format like
      this:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Cách tạo mã vạch PDF417 trong C# với Aspose.BarCode
url: /vi/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 trong C# với Aspose.BarCode

Nếu bạn cần **tạo mã vạch PDF417** trong một ứng dụng .NET, hướng dẫn này sẽ cho bạn một giải pháp ngắn gọn, từ đầu đến cuối. Bạn sẽ thấy cách tạo mã vạch, tinh chỉnh kích thước và ghi kết quả ra tệp PNG — tất cả đều sử dụng thư viện Aspose.BarCode.

Việc tạo mã vạch PDF417 thường gặp khi bạn cần mã hoá lượng lớn dữ liệu để quét trên thiết bị di động, thẻ lên máy bay hoặc nhãn kho. Khi kết thúc tutorial này, bạn sẽ có một chương trình console sẵn sàng chạy, tạo ra hình ảnh PNG chất lượng cao.

## Yêu cầu trước

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Phiên bản mới nhất của **Aspose.BarCode for .NET** (gói NuGet `Aspose.BarCode`)  
* Một IDE hoặc trình soạn thảo (Visual Studio, VS Code, Rider, v.v.)  

Mã này hoạt động trên Windows, Linux và macOS vì Aspose.BarCode hỗ trợ đa nền tảng.

## Bước 1: Tạo dự án console mới

Mở terminal và chạy:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
dotnet add package Aspose.BarCode
```

Lệnh này tạo một dự án C# tối thiểu có tên **Pdf417Demo** và thêm phụ thuộc `Aspose.BarCode`.

## Bước 2: Viết mã tạo mã vạch

Mở **Program.cs** và thay thế nội dung của nó bằng đoạn sau:

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a PDF417 barcode generator with the desired text
            // EncodeTypes.Pdf417 tells Aspose.BarCode which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417, "Sample text for PDF417 barcode");

            // 2️⃣ Adjust barcode dimensions and column count
            // XDimension controls the width of a single module (pixel size).
            // Setting it to 2 pixels yields a compact yet readable barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Columns define how many data columns the barcode will have.
            // A value of 3 works well for short strings; increase for longer data.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Optional: increase error correction level for more robust scanning.
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // 3️⃣ Save the generated barcode as a PNG file
            // The output path can be absolute or relative to the project folder.
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to '{outputPath}'.");
        }
    }
}
```

### Tại sao mỗi dòng lại quan trọng

* **BarcodeGenerator** – lớp cốt lõi tạo hình ảnh mã vạch. Truyền `EncodeTypes.Pdf417` sẽ chọn ký hiệu PDF417.  
* **XDimension.Pixels** – xác định độ rộng thanh nhỏ nhất. Giá trị nhỏ làm ảnh thu nhỏ; giá trị lớn cải thiện khả năng đọc trên máy quét độ phân giải thấp.  
* **Pdf417.Columns** – điều khiển số cột dữ liệu. Nhiều cột tạo mã vạch ngắn hơn nhưng cao hơn; ít cột làm nó rộng hơn.  
* **ErrorCorrectionLevel** – mức cao hơn thêm dữ liệu dư thừa, làm mã vạch chịu lỗi tốt hơn nhưng tăng kích thước.  
* **Save(..., BarCodeImageFormat.Png)** – ghi hình ảnh ra đĩa ở định dạng PNG, một định dạng không mất dữ liệu, lý tưởng cho việc xử lý tiếp theo hoặc nhúng vào tài liệu.

## Bước 3: Biên dịch và chạy chương trình

Từ terminal, thực thi:

```bash
dotnet run
```

Bạn sẽ thấy:

```
PDF417 barcode saved to 'Pdf417Basic.png'.
```

Một tệp có tên **Pdf417Basic.png** sẽ xuất hiện trong thư mục dự án. Khi mở lên, bạn sẽ thấy mã vạch PDF417 rõ ràng mã hoá văn bản *“Sample text for PDF417 barcode”*.

![Mã vạch PDF417 đã tạo và lưu dưới dạng tệp PNG](pdf417-barcode-example.png "Mã vạch PDF417 đã tạo ở định dạng PNG")

*Văn bản thay thế hình ảnh: ảnh chụp màn hình của mã vạch PDF417 đã tạo và lưu dưới dạng tệp PNG, minh họa kết quả của hướng dẫn tạo mã vạch PDF417.*

## Bước 4: Các biến thể phổ biến và trường hợp đặc biệt

### Thay đổi dữ liệu được mã hoá

Thay thế đối số thứ hai của `BarcodeGenerator` bằng bất kỳ chuỗi UTF‑8 nào, ví dụ:

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "https://example.com/checkout?order=12345")
```

### Điều chỉnh kích thước ảnh mà không mất chất lượng

Nếu bạn cần ảnh lớn hơn để in, tăng giá trị `XDimension.Pixels`:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // double the module width
```

### Xử lý đầu vào rất dài

PDF417 có thể mã hoá tới 1 850 ký tự. Đối với chuỗi cực dài, bạn có thể muốn tăng số cột:

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 5; // more columns, less height
```

Nếu nội dung vượt quá dung lượng tối đa, Aspose.BarCode sẽ ném ra `ArgumentException`. Bao quanh mã tạo trong khối try‑catch để hiển thị thông báo lỗi thân thiện.

### Lưu ở các định dạng khác

Aspose.BarCode hỗ trợ BMP, JPEG, TIFF và SVG. Thay đổi định dạng như sau:

```csharp
generator.Save("Pdf417Vector.svg", BarCodeImageFormat.Svg);
```

## Bước 5: Xác minh mã vạch

Bạn có thể xác nhận mã vạch hợp lệ bằng cách quét nó bằng bất kỳ ứng dụng đọc PDF417 nào (ví dụ, ứng dụng camera trên điện thoại hỗ trợ quét mã vạch). Văn bản giải mã phải khớp với chuỗi bạn đã truyền cho trình tạo.

Nếu việc quét không thành công:

* Đảm bảo ảnh không bị nén (sử dụng PNG hoặc SVG không mất dữ liệu).  
* Kiểm tra `ErrorCorrectionLevel` đủ cao cho môi trường dự kiến.  
* Kiểm tra kích thước mã vạch phù hợp với độ phân giải của máy quét.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch PDF417** trong C# bằng Aspose.BarCode, tùy chỉnh kích thước, đặt số cột và xuất kết quả dưới dạng ảnh PNG. Cách tiếp cận này hoạt động trong nhiều tình huống, từ vé điện tử di động đến quản lý tồn kho.

Tiếp theo, bạn có thể khám phá:

* **Đọc** mã vạch PDF417 bằng `BarCodeReader`.  
* Tạo các ký hiệu khác như QR Code hoặc DataMatrix.  
* Nhúng PNG vào PDF, báo cáo hoặc trang web.  

Hãy tự do thử nghiệm các mức sửa lỗi, định dạng ảnh và dữ liệu khác nhau để phù hợp với nhu cầu dự án của bạn. Chúc lập trình vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?

Các tutorial sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoàn chỉnh kèm giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch PDF417 trong C# với Aspose.BarCode BarcodeGenerator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/)
- [Cách tạo mã vạch PDF417 và hiển thị dưới dạng PNG](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/)
- [Cách tạo mã vạch PDF417 trong C# và đặt kích thước mã vạch](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}