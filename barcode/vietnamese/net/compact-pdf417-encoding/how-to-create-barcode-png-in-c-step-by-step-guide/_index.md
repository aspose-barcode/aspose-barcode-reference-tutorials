---
category: general
date: 2026-10-15
description: Tạo mã vạch PNG trong C# với ví dụ PDF417 gọn – tìm hiểu cách đặt cột,
  điều chỉnh kích thước và tạo hình ảnh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: vi
lastmod: 2026-10-15
og_description: Tạo mã vạch PNG trong C# với ví dụ PDF417 gọn nhẹ. Hướng dẫn này chỉ
  cách đặt số cột, điều chỉnh kích thước và lưu hình ảnh.
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: Tạo mã vạch PNG trong C# – hướng dẫn lập trình đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: Cách tạo mã vạch PNG trong C# – hướng dẫn từng bước
url: /vi/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo barcode PNG trong C# – hướng dẫn từng bước

Nếu bạn cần **tạo barcode PNG** từ mã C#, hướng dẫn này sẽ cho bạn một giải pháp hoàn chỉnh chỉ trong vài dòng. Bạn sẽ thấy cách đặt số cột, điều chỉnh kích thước module, và lưu một mã PDF417 dạng compact dưới dạng ảnh PNG — tất cả trong một ví dụ đơn giản, dễ hiểu.

Tạo barcode một cách lập trình loại bỏ bước thủ công sử dụng trình chỉnh sửa đồ họa, và cho phép bạn nhúng barcode trực tiếp vào hoá đơn, vé, hoặc nhãn kho. Trong các phần tiếp theo, chúng tôi sẽ đề cập đến mọi thứ bạn cần biết để **cách tạo barcode** ảnh, lý do mỗi cấu hình quan trọng, và cách điều chỉnh mã cho các trường hợp sử dụng khác nhau.

## Yêu cầu trước

* .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+)
* Tham chiếu tới một thư viện barcode hỗ trợ PDF417, chẳng hạn như **Aspose.BarCode for .NET** hoặc **IronBarcode**. Ví dụ này sử dụng Aspose.BarCode, bạn có thể cài đặt qua NuGet:

```bash
dotnet add package Aspose.BarCode
```

* Kiến thức cơ bản về cú pháp C# và Visual Studio (hoặc bất kỳ IDE nào bạn thích).

> **Mẹo:** Nếu bạn muốn một lựa chọn miễn phí, thư viện mã nguồn mở **ZXing.Net** cũng hỗ trợ PDF417, nhưng tên thuộc tính có chút khác nhau. Các khái niệm được trình bày ở đây vẫn giữ nguyên.

## Cách tạo barcode PNG trong C# (bước chính)

Cốt lõi của giải pháp là một đối tượng `BarcodeGenerator` được cấu hình cho mã hoá PDF417. Các phần sau sẽ phân tích từng dòng mã, giải thích **cách đặt cột**, và chỉ ra tại sao các thiết lập ảnh hưởng đến kích thước PNG cuối cùng.

### Bước 1: Khởi tạo trình tạo barcode với văn bản mong muốn

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*Tại sao điều này quan trọng*: Enum `EncodeTypes.Pdf417` báo cho thư viện tạo một barcode 2‑chiều dạng xếp chồng. Hàm khởi tạo cũng nhận dữ liệu bạn muốn mã hoá, vì vậy không cần gọi riêng `SetData`.

### Bước 2: Đặt kích thước module (X) tính bằng pixel

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Kích thước X** kiểm soát mật độ hình ảnh của barcode. Giá trị nhỏ hơn tạo ra hình ảnh chặt hơn, hữu ích khi bạn cần PNG dạng compact cho màn hình di động hoặc không gian in hạn chế.

### Bước 3: Xác định số cột cho barcode PDF417

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

Dòng này minh họa **cách đặt cột**. PDF417 có thể tự động chọn số cột tối ưu, nhưng việc đặt rõ ràng giúp bạn có chiều rộng dự đoán được, đặc biệt khi nhúng PNG vào bố cục có kích thước cố định.

### Bước 4: Kích hoạt bố cục compact bằng cách cắt ngắn barcode

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

Khi `Truncate` được đặt true, thư viện sẽ loại bỏ các hàng cuối không chứa dữ liệu, giảm chiều cao tổng thể của ảnh mà không mất thông tin.

### Bước 5: Lưu ảnh barcode dưới dạng PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Phương thức `Save` ghi barcode ra đĩa ở định dạng bạn chỉ định. PNG là không mất dữ liệu, rất phù hợp cho các ứng dụng quét yêu cầu phát hiện cạnh chính xác.

### Ví dụ đầy đủ, có thể chạy

Kết hợp tất cả lại, đây là một chương trình tự chứa mà bạn có thể sao chép, dán và chạy:

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**Kết quả mong đợi** – Sau khi chạy chương trình, bạn sẽ thấy file `CompactPdf417.png` trong thư mục thực thi. Ảnh chứa một barcode PDF417 ba cột, đủ compact để vừa trên nhãn tiêu chuẩn 2 × 2 cm mà vẫn có thể quét được đầy đủ.

![Create barcode PNG example](placeholder.png){alt="Tạo barcode PNG bằng C#"}

## Cách đặt cột cho các kích thước dữ liệu khác nhau (từ khóa phụ)

Số cột ảnh hưởng đến cả chiều rộng và khả năng đọc của barcode:

| Cột | Chiều rộng xấp xỉ (px) | Trường hợp sử dụng điển hình |
|--------|-------------------|------------------|
| 1‑2    | Narrow, tall      | Small tags, RFID‑like prints |
| 3‑5    | Balanced          | General‑purpose labels |
| 6‑9    | Wide, short       | Large posters or packaging |

Nếu chuỗi dữ liệu của bạn dài hơn, thư viện có thể tự động tăng số hàng để giữ barcode trong giới hạn cột. Tuy nhiên, ép buộc một số cột quá thấp có thể làm barcode trở nên quá cao, có thể không vừa trên máy in biên lai. Hãy điều chỉnh số cột dựa trên các ràng buộc vật lý của phương tiện xuất ra.

## Cách tạo ảnh barcode ở các định dạng khác (từ khóa phụ)

Mặc dù PNG là định dạng phổ biến nhất cho web và di động, bạn có thể cần **cách tạo barcode** ảnh ở định dạng JPEG, BMP, hoặc SVG cho các quy trình chuyên biệt:

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

Lựa chọn định dạng phù hợp phụ thuộc vào người tiêu thụ downstream:

* **PNG** – không mất dữ liệu, lý tưởng cho máy quét.
* **JPEG** – kích thước tệp nhỏ hơn, chấp nhận được khi một chút nhiễu nén là chấp nhận được.
* **SVG** – hoàn hảo cho in độ phân giải cao hoặc phóng to giao diện người dùng.

## Ví dụ barcode C#: xử lý lỗi và các trường hợp biên

Một **ví dụ barcode C#** mạnh mẽ nên dự đoán các vấn đề thời gian chạy:

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*Tại sao bọc trong `try/catch`?* Các ký tự không hợp lệ trong văn bản, kích thước không hỗ trợ, hoặc vấn đề quyền ghi sẽ ném ngoại lệ. Xử lý chúng một cách nhẹ nhàng ngăn ứng dụng của bạn bị sập trong quá trình xử lý hàng loạt.

## Mở rộng ví dụ: thêm logo hoặc nền

Nhiều tình huống thực tế yêu cầu lớp phủ logo hoặc nền màu. API Aspose.BarCode cho phép bạn kết hợp barcode với bitmap:

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

Kỹ thuật này giữ nguyên quy trình **tạo barcode PNG** đồng thời làm phong phú thương hiệu hình ảnh cuối cùng.

## Tóm tắt

Trong hướng dẫn này, chúng tôi đã trình bày cách **tạo barcode PNG** trong C# bằng cấu hình PDF417 compact. Bạn đã học được:

* Mã chính xác cần thiết để khởi tạo `BarcodeGenerator`.
* **Cách đặt cột** và lý do số cột quan trọng đối với kích thước và khả năng đọc.
* Cách điều chỉnh kích thước X và bật cắt ngắn để có PNG chặt hơn.
* Các cách lưu ảnh dưới dạng PNG, JPEG, hoặc SVG.
* Mẫu xử lý lỗi cho một **ví dụ barcode C#** sẵn sàng cho sản xuất.
* Các mở rộng tùy chọn như lớp phủ logo và tùy chỉnh nền.

Bạn hiện đã có một đoạn mã sẵn sàng chạy mà có thể tích hợp vào các trình tạo hoá đơn, hệ thống bán vé, hoặc công cụ quản lý kho. Hãy thử nghiệm với các giá trị cột khác nhau, kích thước module, hoặc các loại barcode (ví dụ: QR, Code128) để xem ảnh thay đổi như thế nào.

## Các bước tiếp theo

* Khám phá các loại mã hoá khác (`EncodeTypes.QR`, `EncodeTypes.Code128`) để đáp ứng nhiều trường hợp sử dụng hơn.
* Kết hợp việc tạo barcode với các thư viện tạo PDF (ví dụ, **iTextSharp**) để nhúng PNG trực tiếp vào tài liệu.
* Nghiên cứu kích thước động: tính số cột tối ưu dựa trên độ dài chuỗi đầu vào và kích thước nhãn mục tiêu.

Chúc lập trình vui vẻ, và tận hưởng sự đơn giản của việc tạo barcode PNG sắc nét một cách lập trình trong C#!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo barcode PDF417 và lưu dưới dạng PNG trong C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [Cách tạo barcode PDF417 và đặt kích thước trong C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [Cách tạo barcode PDF417 trong C# với chế độ compact](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}