---
category: general
date: 2026-10-28
description: Cách tạo mã vạch với văn bản tùy chỉnh bằng Aspose.BarCode – hướng dẫn
  chi tiết từng bước cho các nhà phát triển .NET để tạo hình ảnh mã vạch Aspose.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: vi
lastmod: 2026-10-28
og_description: Cách tạo mã vạch với văn bản tùy chỉnh trong .NET bằng Aspose.BarCode.
  Theo dõi hướng dẫn đầy đủ này để tạo và lưu mã vạch Macro PDF417.
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: Cách tạo mã vạch với văn bản tùy chỉnh – Hướng dẫn Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: Cách tạo mã vạch với văn bản tùy chỉnh bằng Aspose.BarCode cho .NET
url: /vi/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch với văn bản tùy chỉnh bằng Aspose.BarCode cho .NET

Việc tạo mã vạch với văn bản tùy chỉnh là một yêu cầu thường gặp khi bạn cần nhúng các định danh, dấu thời gian hoặc các siêu dữ liệu khác trực tiếp vào một mã hình ảnh. Hướng dẫn này sẽ chỉ cho bạn cách tạo mã vạch Macro PDF417 chứa văn bản tùy chỉnh và một bộ siêu dữ liệu đầy đủ, sử dụng thư viện **Aspose.BarCode** cho .NET.

Bạn sẽ học cách cấu hình trình tạo, áp dụng văn bản tùy chỉnh, thiết lập các trường riêng của Macro PDF417, và lưu kết quả dưới dạng ảnh PNG. Không cần công cụ bên ngoài—chỉ cần gói NuGet Aspose.BarCode và môi trường phát triển .NET.

## Yêu cầu trước

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ .NET)  
* Gói NuGet **Aspose.BarCode for .NET** (`Install-Package Aspose.BarCode`)  

Những yêu cầu này đảm bảo mã có thể biên dịch và chạy mà không cần cấu hình bổ sung.

## Bước 1: Cài đặt gói Aspose.BarCode

Mở terminal trong thư mục dự án của bạn và chạy:

```bash
dotnet add package Aspose.BarCode
```

Lệnh này sẽ thêm phiên bản ổn định mới nhất của Aspose.BarCode vào dự án của bạn, cung cấp quyền truy cập vào lớp `BarcodeGenerator` và tất cả các tham số liên quan.

## Bước 2: Tạo một ứng dụng console mới

Tạo một ứng dụng console tối thiểu để chứa logic tạo mã vạch:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### Tại sao mỗi dòng lại quan trọng

* **EncodeTypes.MacroPdf417** – chọn ký hiệu Macro PDF417, hỗ trợ dữ liệu phân đoạn và siêu dữ liệu.  
* **XDimension.Pixels** – điều khiển kích thước của mỗi mô-đun; giá trị 2 pixel tạo ra hình ảnh rõ ràng, có thể quét được.  
* **Pdf417.Columns** – giảm chiều rộng tổng thể, làm cho mã vạch gọn hơn cho nhãn in.  
* **MacroPdf417* properties** – nhúng thông tin cấp tệp (ID, số đoạn, dấu thời gian, v.v.) trực tiếp vào mã vạch. Khả năng này là duy nhất của Macro PDF417 và thường được sử dụng trong hệ thống logistics hoặc quản lý tài liệu.  
* **Save(..., BarCodeImageFormat.Png)** – ghi file PNG không mất dữ liệu, giữ các cạnh sắc nét của mã vạch để quét đáng tin cậy.

## Bước 3: Chạy chương trình và xác minh đầu ra

Biên dịch và thực thi ứng dụng console:

```bash
dotnet run
```

Chương trình tạo file `ExtPDF417Meta.png` trong thư mục làm việc của dự án. Mở file này sẽ hiển thị một mã vạch Macro PDF417 mã hoá văn bản **“Åspóse.Barcóde©”** cùng với siêu dữ liệu bạn đã cung cấp.

**Kết quả mong đợi** – một ảnh PNG tương tự như hình dưới đây:

![ví dụ tạo mã vạch đầu ra PNG hiển thị mã vạch Macro PDF417](ExtPDF417Meta.png)

*Văn bản thay thế của hình ảnh (“ví dụ tạo mã vạch đầu ra PNG”) củng cố từ khóa chính cho khả năng truy cập và SEO.*

## Các biến thể phổ biến và trường hợp đặc biệt

### Sử dụng loại mã vạch khác

Nếu bạn cần **tạo mã vạch với văn bản tùy chỉnh** cho mã QR thay vì Macro PDF417, hãy thay thế `EncodeTypes.MacroPdf417` bằng `EncodeTypes.QR`. Cấu trúc các tham số còn lại giữ nguyên, nhưng mã QR không hỗ trợ các trường siêu dữ liệu Macro.

### Xử lý ký tự Unicode

Ví dụ đã bao gồm các ký tự Unicode (`Å`, `ó`, `©`). Aspose.BarCode hỗ trợ đầu vào UTF‑8 ngay từ đầu, nhưng bạn nên đảm bảo file nguồn được lưu với mã hóa UTF‑8 để tránh cảnh báo khi biên dịch.

### Lưu dưới các định dạng ảnh khác

Aspose.BarCode hỗ trợ BMP, JPEG, TIFF và SVG ngoài PNG. Thay đổi giá trị enum `BarCodeImageFormat` cho phù hợp:

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### Bộ dữ liệu lớn

Macro PDF417 có thể chia dữ liệu thành nhiều đoạn. Khi văn bản vượt quá khả năng của một đoạn duy nhất, tăng `MacroPdf417SegmentID` và giữ `MacroPdf417SegmentsCount` đồng nhất trên tất cả các phần được tạo. Cách tiếp cận này là cần thiết cho các kịch bản **create barcode aspose** khi tải trọng lớn hơn một mã vạch có thể chứa.

### Xử lý lỗi

Bao quanh logic tạo mã vạch trong khối try‑catch để phát hiện các vấn đề thời gian chạy như đường dẫn tệp không hợp lệ hoặc ký tự không được hỗ trợ:

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## Mẹo chuyên nghiệp để tạo mã vạch đáng tin cậy

* **Xác thực mã vạch** sau khi tạo bằng `BarCodeReader`. Bước bổ sung này xác nhận dữ liệu đã mã hoá khớp với mong đợi của bạn.

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **Giữ X‑dimension trong khoảng 2 – 4 pixel** cho hầu hết các máy quét. Giá trị nhỏ hơn có thể tạo ra hình ảnh không đọc được trên thiết bị độ phân giải thấp.

* **Tránh tên tệp quá dài** trong `MacroPdf417FileName`. Quy chuẩn giới hạn trường này ở 32 ký tự.

* **Sử dụng dấu thời gian nhất quán** (UTC) khi tạo nhiều đoạn để đơn giản hoá quá trình xử lý phía sau.

## Kết luận

Bây giờ bạn đã biết **cách tạo mã vạch** với văn bản tùy chỉnh bằng Aspose.BarCode cho .NET, cách cấu hình siêu dữ liệu Macro PDF417, và cách lưu kết quả dưới dạng ảnh PNG. Ví dụ đầy đủ, có thể chạy này minh họa mọi bước cần thiết—từ cài đặt gói NuGet đến xử lý ký tự Unicode và lưu đầu ra.

Từ đây bạn có thể:

* **Tạo mã vạch với văn bản tùy chỉnh** cho các ký hiệu khác (QR, DataMatrix, v.v.)  
* **Tạo quy trình làm việc barcode Aspose** để xử lý hàng nghìn ảnh theo lô  
* Tích hợp mã tạo mã vạch vào các dịch vụ ASP.NET Core, Windows service, hoặc Azure Functions  

Thử nghiệm với các tham số khác nhau, khám phá các trường siêu dữ liệu bổ sung, và tích hợp mã vạch vào quy trình tự động hoá tài liệu của bạn. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch PDF417 với Aspose – Hướng dẫn chi tiết từng bước](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Tạo mã vạch từ văn bản bằng Aspose.BarCode – Hướng dẫn C#](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [Cách sử dụng Aspose.BarCode để tạo văn bản mã DataMatrix trong .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}