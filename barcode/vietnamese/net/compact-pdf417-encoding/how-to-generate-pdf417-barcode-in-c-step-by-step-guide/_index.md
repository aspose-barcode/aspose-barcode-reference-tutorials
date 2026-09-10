---
category: general
date: 2026-09-10
description: Tạo mã vạch PDF417 trong C# nhanh chóng. Tìm hiểu cách tạo PDF417 và
  cách thay đổi kích thước mã vạch với Aspose.BarCode chỉ trong vài dòng.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: vi
lastmod: 2026-09-10
og_description: Tạo mã vạch PDF417 trong C# ngay lập tức. Hướng dẫn này cho thấy cách
  tạo PDF417 và cách thay đổi kích thước mã vạch bằng Aspose.BarCode.
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: Tạo mã vạch PDF417 trong C# – hướng dẫn lập trình đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Cách tạo mã vạch PDF417 trong C# – hướng dẫn từng bước
url: /vi/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo PDF417 barcode trong C# – hướng dẫn từng bước

Nếu bạn cần **tạo PDF417 barcode** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chính xác. Bạn sẽ thấy một ví dụ ngắn gọn, sẵn sàng chạy tạo PDF417 barcode, cho phép bạn kiểm soát kích thước của nó và lưu kết quả dưới dạng ảnh PNG.

Việc tạo PDF417 barcode là một yêu cầu phổ biến cho các hệ thống quản lý tồn kho, vé lên máy bay và theo dõi tài liệu. Trong hướng dẫn này, chúng tôi cũng sẽ đề cập đến **cách thay đổi kích thước mã vạch** để mã có thể thích nghi với các nhu cầu in ấn hoặc hiển thị trên màn hình khác nhau.

## Yêu cầu trước

* .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.6+)
* Visual Studio 2022 hoặc bất kỳ IDE C# nào
* Gói NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Kiến thức cơ bản về các ứng dụng console C#

## Cài đặt dự án

1. Tạo một dự án console mới:

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. Thêm tham chiếu Aspose.BarCode (xem mục yêu cầu trước).  

3. Mở `Program.cs` và thay thế nội dung của nó bằng ví dụ đầy đủ dưới đây.

## Bước 1: Tạo PDF417 barcode

Bước đầu tiên là tạo một thể hiện `BarcodeGenerator` được cấu hình cho ký hiệu **PDF417**. Đối tượng này là điểm khởi đầu cho tất cả các thao tác với mã vạch.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*Why this matters* – Giá trị enum `EncodeTypes.Pdf417` thông báo cho Aspose.BarCode sử dụng tiêu chuẩn PDF417, trong khi đối số thứ hai cung cấp dữ liệu sẽ được mã hoá. Bộ tạo bây giờ giữ một đối tượng mã vạch đầy đủ mà bạn có thể tùy chỉnh trước khi lưu.

## Bước 2: Cách thay đổi kích thước mã vạch (kích thước module)

PDF417 barcodes consist of small square modules. Adjusting the module size changes the overall dimensions of the image without altering the encoded data.

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*Why this matters* – `XDimension` lớn hơn tạo ra mã vạch lớn hơn, phù hợp cho việc in độ phân giải cao; giá trị nhỏ hơn thì tốt hơn cho hiển thị trên màn hình. Mặc định thường là 1 px, có thể trông chật chội trên các màn hình hiện đại.

## Bước 3: Cấu hình bố cục – cột và hàng

PDF417 cho phép bạn xác định số cột và hàng, điều này ảnh hưởng đến hình dạng của mã vạch và khả năng sửa lỗi của nó.

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*Why this matters* – Nhiều cột hơn làm mã vạch rộng hơn, trong khi nhiều hàng hơn làm nó cao hơn. Điều chỉnh các giá trị này để phù hợp với không gian có sẵn trong giao diện người dùng hoặc nhãn in.

## Bước 4: Lưu ảnh mã vạch

Cuối cùng, ghi mã vạch ra file. Ở đây chúng ta sử dụng PNG vì nó giữ được các cạnh sắc nét và hỗ trợ trong suốt.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

Chạy chương trình sẽ tạo ra `LayoutPdf417.png` trong thư mục đầu ra của dự án. Hình ảnh sẽ trông như sau:

![generate PDF417 barcode example showing 4 columns and 9 rows](https://example.com/images/pdf417-sample.png){#barcode-image alt="ví dụ tạo mã vạch PDF417 với 4 cột và 9 hàng"}

*Tip*: Nếu bạn cần định dạng ảnh khác (JPEG, BMP, TIFF), hãy thay `BarCodeImageFormat.Png` bằng giá trị enum tương ứng.

## Cách tạo PDF417 – nguồn dữ liệu thay thế

Mã ở trên sử dụng một chuỗi được mã hoá cứng `"Layout test"`. Trong các tình huống thực tế, bạn thường lấy dữ liệu từ cơ sở dữ liệu, tệp tin hoặc đầu vào của người dùng.

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

Phần còn lại của các bước (kích thước, bố cục, lưu) vẫn không thay đổi. Điều này minh họa **cách tạo PDF417** từ các nguồn động mà không cần phức tạp thêm.

## Những lỗi thường gặp và cách tránh

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| Mã vạch bị mờ | `XDimension` được đặt quá thấp so với độ phân giải đầu ra | Tăng `XDimension.Pixels` hoặc lưu dưới dạng định dạng vector như SVG (`BarCodeImageFormat.Svg`) |
| Văn bản không vừa trong bố cục đã chọn | Quá nhiều ký tự cho số hàng/cột đã chọn | Giảm số hàng/cột hoặc chia dữ liệu thành nhiều mã vạch |
| File ảnh không được tạo | Thư mục đầu ra không tồn tại hoặc thiếu quyền ghi | Đảm bảo thư mục tồn tại (`Directory.CreateDirectory`) và ứng dụng chạy với quyền phù hợp |

## Xác minh mã vạch

Sau khi tạo ảnh, bạn có thể xác minh nó bằng bất kỳ ứng dụng quét PDF417 nào (điện thoại di động có các trình quét miễn phí) hoặc bằng trình đọc Aspose.BarCode tích hợp:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

Nếu đầu ra khớp với văn bản gốc, quá trình **tạo PDF417 barcode** đã thành công.

## Ví dụ đầy đủ, có thể chạy

Dưới đây là chương trình hoàn chỉnh mà bạn có thể sao chép‑dán vào `Program.cs`. Nó bao gồm tất cả các chỉ thị using, xử lý lỗi và chú thích.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

Chạy chương trình này sẽ in ra:

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

Bây giờ bạn đã có một **giải pháp hoàn chỉnh, tự chứa** để tạo PDF417 barcodes và kiểm soát kích thước của chúng.

## Kết luận

Trong hướng dẫn này, bạn đã học cách **tạo PDF417 barcode** trong C# bằng Aspose.BarCode, cách **thay đổi kích thước mã vạch** bằng cách điều chỉnh X‑dimension, và cách cấu hình cột và hàng để kiểm soát bố cục. Bạn cũng đã thấy cách xác minh kết quả bằng chương trình và cách điều chỉnh mã cho dữ liệu động.

Tiếp theo, bạn có thể khám phá:

* **Cách tạo PDF417** với việc điều chỉnh mức độ sửa lỗi (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* Xuất ra **định dạng vector** (SVG, EPS) để phóng to vô hạn
* Nhúng mã vạch vào tài liệu PDF với **Aspose.PDF**

Thử nghiệm với các kích thước module và tùy chọn bố cục khác nhau để phù hợp với giao diện người dùng hoặc yêu cầu in ấn cụ thể của bạn. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoàn chỉnh, hoạt động với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch PDF417 với Aspose – Hướng dẫn đầy đủ](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [điều chỉnh kích thước mã vạch – Hướng dẫn C# để tạo PDF417 barcodes](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [Cách lưu mã vạch trong C# – Tạo PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}