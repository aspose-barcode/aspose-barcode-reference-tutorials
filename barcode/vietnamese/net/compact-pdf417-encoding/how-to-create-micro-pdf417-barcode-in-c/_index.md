---
category: general
date: 2026-11-14
description: Tạo mã vạch micro PDF417 bằng C# với Aspose.BarCode – hướng dẫn chi tiết
  từng bước về cài đặt trình tạo, kích thước X, số cột và xuất PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: vi
lastmod: 2026-11-14
og_description: Tạo mã vạch micro PDF417 bằng C# sử dụng Aspose.BarCode. Tìm hiểu
  cách cấu hình trình tạo, đặt XDimension, chọn số cột và xuất ra PNG.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Tạo mã vạch micro PDF417 bằng C# – hướng dẫn lập trình đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: Cách tạo mã vạch micro PDF417 trong C#
url: /vi/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch micro PDF417 trong C#  

Nếu bạn cần **tạo mã vạch micro PDF417** nhanh chóng, hướng dẫn này sẽ cho bạn một giải pháp hoàn chỉnh, sẵn sàng chạy. Bạn sẽ thấy cách khởi tạo trình tạo mã vạch, cấu hình kích thước X, chọn số cột, và cuối cùng lưu kết quả dưới dạng ảnh PNG—tất cả đều sử dụng thư viện Aspose.BarCode cho .NET.

Việc tạo mã vạch micro PDF417 không đòi hỏi một quy trình xây dựng phức tạp. Khi kết thúc tutorial này, bạn sẽ có một tệp C# duy nhất tạo ra hình ảnh mã vạch chất lượng cao mà bạn có thể nhúng vào báo cáo, nhãn mác hoặc ứng dụng di động.

## Yêu cầu trước  

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+).  
* Môi trường phát triển như Visual Studio 2022, VS Code, hoặc Rider.  
* Giấy phép Aspose.BarCode cho .NET (hoặc khóa dùng thử miễn phí). Bạn có thể lấy nó từ [trang web Aspose](https://purchase.aspose.com/barcode/net).  

> **Mẹo chuyên nghiệp:** Nếu bạn đang dùng phiên bản dùng thử, file PNG được tạo sẽ chứa một watermark “Evaluation” nhỏ. Phiên bản có giấy phép sẽ tự động loại bỏ watermark này.

## Bước 1: Thiết lập dự án  

Tạo một dự án console mới và thêm gói NuGet Aspose.BarCode.

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

Lệnh `dotnet add package` sẽ tải các phụ thuộc **Aspose.BarCode C# example**, vì vậy bạn không cần quản lý các DLL thủ công.

## Bước 2: Viết toàn bộ mã  

Thay thế tệp `Program.cs` được tạo tự động bằng đoạn mã sau. Nó minh họa cách **tạo micro pdf417 barcode** từ đầu đến cuối.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### Tại sao mỗi dòng lại quan trọng  

* **BarcodeGenerator constructor** – Khởi tạo **trình tạo mã vạch micro pdf417** với văn bản bạn muốn mã hoá.  
* **XDimension.Pixels** – Kiểm soát chiều rộng mô-đun; đặt thành `2` pixel sẽ cho ra một mã vạch dày đặc, độ phân giải cao, phù hợp với hầu hết máy quét.  
* **Pdf417.Columns** – MicroPDF417 chỉ hỗ trợ 1‑4 cột. Chọn `4` sẽ giảm chiều cao mã vạch, hữu ích khi không gian dọc bị hạn chế.  
* **Save method** – Ghi mã vạch ra file PNG. PNG là định dạng lossless, đảm bảo máy quét đọc đúng mẫu bạn đã tạo.

## Bước 3: Biên dịch và chạy  

Biên dịch và thực thi chương trình:

```bash
dotnet run
```

Bạn sẽ thấy đầu ra trên console:

```
Micro PDF417 barcode saved to MicroPdf417.png
```

Một tệp có tên **MicroPdf417.png** sẽ xuất hiện trong thư mục dự án. Mở nó bằng bất kỳ trình xem ảnh nào; bạn sẽ thấy một mã vạch micro PDF417 sắc nét mã hoá chuỗi `"Åspóse.Barcóde©"`.

![Ví dụ mã vạch micro PDF417 được tạo](MicroPdf417.png "Ví dụ mã vạch micro PDF417 được tạo"){.center-image width=400 alt="Ví dụ hình ảnh mã vạch micro PDF417 được tạo"}

*Hình ảnh trên là kết quả của đoạn mã được hiển thị ở Bước 2.*

## Bước 4: Các biến thể phổ biến và trường hợp đặc biệt  

| Tình huống | Cách điều chỉnh mã |
|-----------|----------------------|
| **Độ dài dữ liệu khác** | MicroPDF417 có thể mã hoá tới 1 200 ký tự. Chỉ cần thay đổi đối số thứ hai của `BarcodeGenerator`. |
| **Độ phân giải cao hơn** | Tăng `XDimension.Pixels` lên `3` hoặc `4`. Các mô-đun lớn hơn cải thiện khả năng đọc trên máy quét độ phân giải thấp nhưng làm tăng kích thước ảnh. |
| **Màu sắc tùy chỉnh** | Sau khi tạo generator, đặt `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` và `generator.Parameters.Barcode.BackgroundColor = Color.White;`. |
| **Lưu dưới định dạng khác** | Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, hoặc `Gif` tùy theo yêu cầu downstream của bạn. |
| **Nhúng vào PDF** | Dùng `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);` rồi hợp nhất PDF với các tài liệu khác bằng Aspose.PDF. |

> **Cảnh báo:** Đặt `XDimension.Pixels` dưới `1` sẽ ném ra `ArgumentOutOfRangeException`. Luôn giữ giá trị từ `1` trở lên.

## Bước 5: Xác minh mã vạch  

Để chắc chắn mã vạch được quét đúng:

1. Mở file PNG trong trình xem ảnh.  
2. Sử dụng bất kỳ ứng dụng quét mã vạch trên smartphone nào hỗ trợ PDF417 (hầu hết các “QR‑code scanner” đều có hỗ trợ).  
3. Quét ảnh; ứng dụng sẽ hiển thị lại văn bản gốc `"Åspóse.Barcóde©"`.

Nếu quét không thành công, hãy kiểm tra lại **kích thước X‑dimension** và **cài đặt cột** – mô-đun quá nhỏ hoặc số cột không được hỗ trợ có thể làm mẫu không đọc được.

## Kết luận  

Bây giờ bạn đã biết cách **tạo micro pdf417 barcode** trong C# bằng Aspose.BarCode. Tutorial đã bao gồm:

* Khởi tạo **trình tạo mã vạch micro pdf417**.  
* **Đặt XDimension pixels** để điều chỉnh chiều rộng mô-đun.  
* **Xác định số cột của mã vạch** để thay đổi hình dạng.  
* **Lưu mã vạch dưới dạng PNG** để có đầu ra ảnh lossless.  

Từ đây, bạn có thể khám phá các tính năng bổ sung như tùy chỉnh màu sắc, nhúng mã vạch vào PDF, hoặc tạo mã vạch động trong các API web ASP.NET Core. Chúc bạn lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên đều bao gồm mã mẫu đầy đủ với giải thích chi tiết từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Create barcode PNG in C# – full guide to GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [Create PDF417 barcode in C# using Aspose.BarCode – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}