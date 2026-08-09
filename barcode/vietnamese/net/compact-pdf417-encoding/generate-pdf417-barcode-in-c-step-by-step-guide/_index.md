---
category: general
date: 2026-08-09
description: Tạo mã vạch PDF417 trong C# nhanh chóng. Tìm hiểu cách tạo PDF417 với
  chế độ nén, kiểm soát cột và xuất PNG bằng API BarcodeGenerator.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create pdf417 barcode c#
- barcode generator c#
- compact pdf417 settings
- pdf417 png output
language: vi
lastmod: 2026-08-09
og_description: Tạo mã vạch PDF417 trong C# với một ví dụ ngắn gọn. Hướng dẫn này
  chỉ cho bạn cách cấu hình chế độ compact, đặt số cột và lưu kết quả dưới dạng ảnh
  PNG.
og_image_alt: Generated PDF417 barcode image saved as PNG
og_title: Tạo mã vạch PDF417 bằng C# – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    with compact mode, column control, and PNG output using the BarcodeGenerator API.
  headline: Generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- pdf417
- C#
- Aspose.BarCode
title: Tạo mã vạch PDF417 trong C# – hướng dẫn từng bước
url: /vi/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch PDF417 trong C# – hướng dẫn từng bước

Nếu bạn cần **tạo mã vạch PDF417** trong một ứng dụng .NET, bài hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Bạn sẽ thấy một chương trình đầy đủ, có thể chạy được, tạo một mã vạch PDF417 gọn gàng, tùy chỉnh kích thước và lưu hình ảnh dưới dạng file PNG.

Việc tạo mã vạch PDF417 là yêu cầu phổ biến cho vé điện thoại di động, theo dõi tồn kho và bảo mật tài liệu. Hướng dẫn này bao gồm các tùy chọn cấu hình thiết yếu, giải thích lý do mỗi thiết lập quan trọng và cung cấp các mẹo thực tiễn cho việc sử dụng trong thực tế.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Một IDE C# như Visual Studio 2022 hoặc Visual Studio Code  
* Gói **Aspose.BarCode for .NET** từ NuGet (phiên bản 23.10 hoặc mới hơn)  

Bạn có thể cài đặt gói bằng lệnh CLI sau:

```bash
dotnet add package Aspose.BarCode
```

Mã dưới đây giả định rằng gói đã được tham chiếu và bạn có quyền ghi vào thư mục đầu ra.

## Bước 1: Thiết lập dự án và nhập các namespace

Tạo một dự án console mới và thêm các chỉ thị `using` cần thiết. Các namespace này cung cấp lớp `BarcodeGenerator` và kiểu liệt kê định dạng ảnh.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;
```

**Tại sao lại quan trọng:** Việc nhập đúng namespace giúp trình biên dịch tìm thấy kiểu `BarcodeGenerator` và enum `BarCodeImageFormat`. Thiếu namespace sẽ gây lỗi biên dịch, làm dừng quá trình tạo mã vạch.

## Bước 2: Khởi tạo `BarcodeGenerator` với mã hoá PDF417

Constructor của `BarcodeGenerator` nhận hai đối số: loại mã vạch (`EncodeTypes.Pdf417`) và chuỗi bạn muốn mã hoá. PDF417 hỗ trợ một dải ký tự rộng, bao gồm các ký tự Unicode.

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**Giải thích:**  
* `EncodeTypes.Pdf417` báo cho thư viện sử dụng chuẩn PDF417.  
* Văn bản mẫu chứa các ký tự có dấu và ký hiệu bản quyền để minh họa việc xử lý Unicode.  

Nếu bạn chỉ cần mã hoá dữ liệu số, có thể truyền một chuỗi đơn giản như `"1234567890"`.

## Bước 3: Điều chỉnh X‑dimension để tăng độ phân giải

X‑dimension kiểm soát độ rộng của một mô-đun mã vạch (phần tử đen hoặc trắng nhỏ nhất). Đặt giá trị pixel nhỏ hơn sẽ cho ra hình ảnh có độ phân giải cao hơn.

```csharp
// Step 3: Adjust the module (X) dimension for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tại sao cần điều chỉnh?** X‑dimension mặc định 3–4 pixel có thể tạo ra mã vạch trông thô trên màn hình DPI cao. Giảm xuống **2 pixel** giúp cân bằng giữa khả năng đọc và kích thước file, đặc biệt khi bạn bật chế độ gọn gàng.

## Bước 4: Cấu hình số cột

PDF417 cho phép bạn chỉ định số cột mà mã vạch sẽ chứa. Ít cột hơn làm mã vạch hẹp hơn nhưng cao hơn, trong khi nhiều cột hơn tạo ra mã vạch rộng hơn, thấp hơn.

```csharp
// Step 4: Set the number of columns to control the barcode width
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

**Mẹo thực tế:** Đối với vé di động cần vừa trong một nhãn hẹp, số cột **3–5** thường hoạt động tốt. Tăng số cột nếu bạn có nhiều dữ liệu và muốn mã vạch ngắn hơn.

## Bước 5: Bật chế độ compact để cắt bỏ các hàng trống

Chế độ compact loại bỏ các hàng không cần thiết khỏi ma trận mã vạch, giảm kích thước ảnh tổng thể mà không mất dữ liệu đã mã hoá.

```csharp
// Step 5: Enable compact mode to truncate the barcode and reduce size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

**Khi nào nên dùng:** Nếu bạn tạo mã vạch để lưu trữ hoặc truyền qua mạng, chế độ compact có thể giảm kích thước file PNG tới 30 %. Tuy nhiên, một số máy quét cũ có thể không hỗ trợ PDF417 đã bị cắt; hãy kiểm tra với phần cứng mục tiêu của bạn.

## Bước 6: Lưu mã vạch dưới dạng ảnh PNG

Chọn đường dẫn đầu ra và gọi `Save`. Kiểu liệt kê `BarCodeImageFormat.Png` tạo ra ảnh không mất dữ liệu, phù hợp với hầu hết các ứng dụng.

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

**Xác minh kết quả:** Mở file PNG bằng bất kỳ trình xem ảnh nào. Bạn sẽ thấy một mã vạch dày đặc, độ tương phản cao, khớp với văn bản mẫu. Quét ảnh bằng trình đọc PDF417 (ví dụ: ZXing hoặc ứng dụng trên điện thoại) sẽ trả về chuỗi gốc `"Åspóse.Barcóde©"`.

![Generated PDF417 barcode image saved as PNG](compact-pdf417.png "Generated PDF417 barcode in C#")

*Hình ảnh trên minh họa kết quả cuối cùng của mã trong tutorial.*

## Ví dụ đầy đủ, có thể chạy

Kết hợp tất cả các phần lại, đây là một chương trình console hoàn chỉnh mà bạn có thể sao chép, dán và chạy.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using Aspose.BarCode.Image;

namespace Pdf417GeneratorDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with PDF417 encoding
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // 2️⃣ Fine‑tune module size for sharper output
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set a narrow column count to keep the barcode slim
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Activate compact mode to drop empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define where the PNG will be written
            string outputPath = @"C:\Barcodes\CompactPdf417.png";

            // 6️⃣ Save the image
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Kết quả mong đợi

Chạy chương trình sẽ in ra:

```
Barcode saved to C:\Barcodes\CompactPdf417.png
```

File `CompactPdf417.png` chứa một mã vạch PDF417 gọn gàng mã hoá chuỗi Unicode đã cung cấp. Quét ảnh bằng trình đọc PDF417 tiêu chuẩn sẽ trả về chính xác văn bản đó.

## Các biến thể phổ biến và trường hợp đặc biệt

| Tình huống | Điều chỉnh | Lý do |
|-----------|------------|--------|
| **Dữ liệu dài hơn** (ví dụ: > 150 ký tự) | Tăng `generator.Parameters.Barcode.Pdf417.Columns` lên 6‑8 | Thêm cột giúp mã vạch không trở nên quá cao. |
| **Cần nền trong suốt** | Dùng `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageSaveOptions { BackgroundColor = Color.Transparent })` | PNG trong suốt dễ tích hợp hơn vào giao diện UI. |
| **Tạo JPEG cho web** | Thay đổi định dạng thành `BarCodeImageFormat.Jpeg` và tùy chọn `ImageQuality` | JPEG giảm kích thước file nhưng mất độ chính xác không mất dữ liệu. |
| **Xử lý đầu vào null hoặc rỗng** | Kiểm tra đầu vào trước khi tạo generator: `if (string.IsNullOrEmpty(text)) throw new ArgumentException("Text cannot be empty.");` | Ngăn lỗi thời gian chạy và đảm bảo mã vạch có ý nghĩa. |

## Mẹo cho môi trường production

* **Xử lý ngoại lệ:** Bao bọc logic tạo mã trong khối `try/catch` để ghi log lỗi như không đủ dung lượng đĩa hoặc tham số không hợp lệ.  
* **Hiệu năng:** Tái sử dụng một thể hiện `BarcodeGenerator` duy nhất khi tạo nhiều mã vạch với cùng cài đặt; chỉ cập nhật thuộc tính `CodeText` giữa các lần lưu.  
* **Bảo mật:** Khi văn bản đã mã hoá chứa thông tin nhạy cảm, cân nhắc mã hoá trước khi truyền vào generator và giải mã sau khi quét.  

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch PDF417** trong C# bằng thư viện Aspose.BarCode, cấu hình chế độ compact, điều chỉnh số cột và xuất kết quả dưới dạng ảnh PNG. Tutorial này đã bao phủ mọi bước từ thiết lập dự án đến xử lý các trường hợp đặc biệt, cung cấp cho bạn một giải pháp sẵn sàng sử dụng cho các ứng dụng dựa trên mã vạch.

Tiếp theo, khám phá các chủ đề liên quan như **tạo mã QR trong C#**, **tạo hàng loạt mã vạch**, và **tích hợp quét mã vạch với ứng dụng di động**. Mỗi chủ đề đều dựa trên các nguyên tắc cơ bản của `BarcodeGenerator` mà bạn vừa nắm vững.

Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ, kèm theo giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch PDF417 – Mã hoá PDF417 Compact](/barcode/english/net/compact-pdf417-encoding/)
- [Cách tạo mã vạch – PDF417 Compact với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách tạo mã vạch Aztec với tỷ lệ khung tùy chỉnh bằng Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}