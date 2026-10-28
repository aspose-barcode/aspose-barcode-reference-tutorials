---
category: general
date: 2026-10-28
description: Tạo mã vạch từ văn bản trong C# với Aspose.BarCode. Tìm hiểu cách tạo
  hình ảnh mã vạch PDF417, thiết lập số cột, điều chỉnh kích thước X và bật chế độ
  compact.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate barcode c#
- generate pdf417 barcode
- pdf417 barcode image
language: vi
lastmod: 2026-10-28
og_description: Tạo mã vạch từ văn bản trong C# bằng Aspose.BarCode. Hướng dẫn này
  cho thấy cách tạo hình ảnh mã vạch PDF417, tùy chỉnh kích thước, số cột và chế độ
  nén.
og_image_alt: Screenshot showing a compact PDF417 barcode created from text using
  C#
og_title: Tạo mã vạch từ văn bản trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Create barcode from text in C# with Aspose.BarCode. Learn to generate
    PDF417 barcode image, set columns, adjust X‑dimension, and enable compact mode.
  headline: How to create barcode from text in C# using Aspose.BarCode
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- image generation
title: Cách tạo mã vạch từ văn bản trong C# bằng Aspose.BarCode
url: /vi/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch từ văn bản trong C# bằng Aspose.BarCode

Nếu bạn cần **tạo mã vạch từ văn bản** trong một ứng dụng .NET, hướng dẫn này cung cấp một giải pháp sẵn sàng chạy. Bạn sẽ thấy cách **tạo ảnh mã vạch PDF417**, kiểm soát độ rộng mô-đun, số cột, và bật chế độ gọn mà không rời khỏi IDE của mình.

Bài hướng dẫn bao gồm mọi thứ cần thiết để **tạo mã vạch C#** code, từ cài đặt thư viện đến lưu tệp PNG cuối cùng. Khi hoàn thành, bạn có thể nhúng một mã vạch PDF417 độ mật độ cao vào báo cáo, vé, hoặc nhãn kho.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ trình soạn thảo nào hỗ trợ .NET)  
* Kết nối Internet để tải gói NuGet Aspose.BarCode cho .NET  

Những mục này đủ để biên dịch và chạy ví dụ trên Windows, Linux hoặc macOS.

## Bước 1: Cài đặt gói NuGet Aspose.BarCode

Thư viện cung cấp khả năng tạo mã vạch là **Aspose.BarCode for .NET**. Cài đặt nó bằng .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

Gói này thêm không gian tên `Aspose.BarCode`, trong đó chứa lớp `BarcodeGenerator` được sử dụng xuyên suốt trong hướng dẫn này.

## Bước 2: Tạo dự án console và thêm mã

Tạo một dự án console mới và thay thế tệp `Program.cs` được tạo tự động bằng đoạn mã sau. Chương trình minh họa cách **tạo mã vạch từ văn bản** và lưu nó dưới dạng **hình ảnh mã vạch PDF417**.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 2.1: Define the text to encode.
            // Unicode characters such as Å, ó, and © are supported out of the box.
            string data = "Åspóse.Barcóde©";

            // Step 2.2: Initialize the PDF417 generator with the desired text.
            // EncodeTypes.Pdf417 tells the generator which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // Step 2.3: Set the X‑dimension (module width) to 2 pixels for a denser barcode.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 2.4: Define the number of columns in the PDF417 symbol.
            // Fewer columns produce a taller barcode; three columns keep it compact.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Step 2.5: Enable compact mode by truncating the right‑hand column.
            // Truncate reduces the overall width while preserving data integrity.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Step 2.6: Choose the output folder and file name.
            string outputPath = "CompactPdf417.png";

            // Step 2.7: Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

### Tại sao mỗi dòng lại quan trọng

* **`EncodeTypes.Pdf417`** chọn ký hiệu PDF417, lý tưởng để mã hoá lượng lớn dữ liệu ở định dạng hai chiều.  
* **`XDimension.Pixels = 2`** giảm độ rộng mô-đun, làm cho mã vạch dày đặc hơn và phù hợp hơn với không gian hạn chế.  
* **`Pdf417.Columns = 3`** điều khiển số cột dữ liệu dọc; số lượng thấp hơn tạo ra mã vạch cao hơn nhưng hẹp hơn.  
* **`Pdf417.Truncate = true`** kích hoạt chế độ gọn, cắt bỏ các cột không dùng ở phía bên phải. Đây là cài đặt quan trọng biến một PDF417 thông thường thành **hình ảnh mã vạch PDF417 gọn**.  

## Bước 3: Xây dựng và chạy dự án

Thực hiện các lệnh sau trong thư mục dự án:

```bash
dotnet build
dotnet run
```

Khi chương trình kết thúc, bạn sẽ thấy một thông báo trên console xác nhận vị trí tệp. Mở `CompactPdf417.png` bằng bất kỳ trình xem ảnh nào để kiểm tra kết quả.

**Kết quả mong đợi** – một tệp PNG độ tương phản cao hiển thị mã vạch PDF417 gọn, mã hoá chuỗi `Åspóse.Barcóde©`. Quét ảnh bằng máy đọc mã vạch tiêu chuẩn sẽ trả về văn bản gốc, xác nhận rằng **tạo mã vạch pdf417** đã thành công.

## Bước 4: Tùy chỉnh mã vạch cho các kịch bản khác nhau

Trong khi ví dụ sử dụng số cột và X‑dimension cố định, bạn có thể điều chỉnh trình tạo cho các yêu cầu khác:

| Kịch bản | Điều chỉnh |
|----------|------------|
| Dữ liệu lớn hơn | Tăng `Pdf417.Columns` hoặc đặt `Pdf417.Rows` thủ công |
| Độ tin cậy quét cao hơn | Tăng `XDimension.Pixels` lên 3 hoặc 4 |
| Định dạng ảnh khác | Thay `BarCodeImageFormat.Png` bằng `Jpeg` hoặc `Bmp` |
| Nền trong suốt | Đặt `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent` |

Các tùy chọn này cho phép bạn **tạo mã vạch C#** giải pháp phù hợp với ứng dụng di động, báo cáo desktop, hoặc dịch vụ web.

## Bước 5: Xử lý các trường hợp đặc biệt và thực hành tốt

* **Hỗ trợ Unicode** – Trình tạo tự động mã hoá các ký tự Unicode, nhưng hãy đảm bảo chuỗi nguồn của bạn được mã hoá UTF‑8 nếu bạn đọc nó từ tệp.  
* **Văn bản lớn** – PDF417 có thể mã hoá tới 1.850 ký tự alphanumeric. Nếu vượt quá giới hạn này, thư viện sẽ ném ngoại lệ; hãy chia dữ liệu thành nhiều mã vạch hoặc chuyển sang ký hiệu có dung lượng cao hơn.  
* **Xử lý lỗi** – Bao quanh mã tạo trong khối `try/catch` để bắt `BarCodeException` và cung cấp thông báo lỗi thân thiện.  
* **Hiệu năng** – Khi tạo nhiều mã vạch trong vòng lặp, việc tái sử dụng một thể hiện `BarcodeGenerator` duy nhất và chỉ cập nhật `CodeText` giữa các lần lặp sẽ cải thiện hiệu suất.  

```csharp
try
{
    generator.CodeText = nextText;
    generator.Save($"barcode_{i}.png", BarCodeImageFormat.Png);
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

## Danh sách mã nguồn đầy đủ

Dưới đây là chương trình hoàn chỉnh, tự chứa, bạn có thể sao chép vào `Program.cs`. Không cần tệp bổ sung nào.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            string data = "Åspóse.Barcóde©";

            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode image saved to {outputPath}");
        }
    }
}
```

Chạy chương trình này sẽ tạo ra **hình ảnh mã vạch pdf417** được hiển thị trong minh họa dưới đây.

![Mã vạch PDF417 gọn được tạo từ văn bản bằng C#](/images/compact-pdf417.png){.img-fluid alt="ví dụ tạo mã vạch từ văn bản hiển thị hình ảnh mã vạch PDF417 gọn"}

*Mô tả hình ảnh: Tệp PNG hiển thị một mã vạch PDF417 gọn, mã hoá chuỗi “Åspóse.Barcóde©”.*  

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch từ văn bản** trong C# và tạo ra một **hình ảnh mã vạch PDF417** với kích thước tùy chỉnh và chế độ gọn. Ví dụ minh họa các bước cần thiết để **tạo mã vạch C#**, xử lý dữ liệu Unicode, và điều chỉnh các tham số hiển thị cho các kịch bản triển khai khác nhau.

Tiếp theo, khám phá các chủ đề liên quan như **tạo mã QR trong C#**, **thêm mã vạch vào tài liệu PDF**, hoặc **nhúng mã vạch trong API ASP.NET Core**. Mỗi chủ đề này dựa trên các nguyên tắc cơ bản của `BarcodeGenerator` đã được đề cập ở đây.

Chúc bạn lập trình vui vẻ, và tận hưởng việc tích hợp mã vạch vào các giải pháp .NET của mình!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ, hoạt động với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo mã vạch PDF417 trong C# – Tạo mã vạch PDF417 C#](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/)
- [Cách tạo mã vạch PDF417 với Aspose.BarCode trong C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-barcode-in-c/)
- [Cách tạo hình ảnh mã vạch PDF417 trong C# – hướng dẫn đầy đủ](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}