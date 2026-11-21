---
category: general
date: 2026-11-20
description: Tạo hình ảnh mã vạch trong C# bằng Aspose.BarCode. Tìm hiểu cách tạo
  mã vạch PDF417 với bố cục tùy chỉnh và lưu dưới dạng PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: vi
lastmod: 2026-11-20
og_description: Tạo hình ảnh mã vạch trong C# với Aspose.BarCode. Hướng dẫn này chỉ
  cách tạo mã vạch PDF417, tùy chỉnh bố cục và xuất ra PNG.
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: Tạo hình ảnh mã vạch PDF417 trong C# – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  headline: How to create barcode image with PDF417 in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  name: How to create barcode image with PDF417 in C# – step‑by‑step guide
  steps:
  - name: Why this code works
    text: '* **`BarcodeGenerator`** is the entry point for all barcode types. By passing
      `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol. * **Columns
      and rows** are the primary levers for layout. Fewer columns produce a taller
      barcode; more columns make it wider. Adjust these values to fit'
  - name: Adjusting data length
    text: 'PDF417 can encode up to 1,850 characters. If you need to encode longer
      strings, consider splitting the data across multiple barcodes or using the **compact
      mode**:'
  - name: Controlling image size
    text: 'The default image size is calculated from the module size (the smallest
      square in the barcode). You can explicitly set the DPI or scale the image after
      generation:'
  - name: Handling special characters
    text: 'PDF417 supports the full ASCII set. If your data contains Unicode characters,
      ensure you encode the string as UTF‑8:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
title: Cách tạo hình ảnh mã vạch PDF417 trong C# – hướng dẫn từng bước
url: /vi/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo hình ảnh mã vạch với PDF417 trong C# – hướng dẫn từng bước

Nếu bạn cần **tạo hình ảnh mã vạch** trong một ứng dụng .NET, hướng dẫn này sẽ cho bạn thấy chính xác **cách tạo mã vạch PDF417** với bố cục tùy chỉnh và lưu nó dưới dạng tệp PNG. Bạn sẽ thấy mã hoàn chỉnh, có thể chạy được, hiểu tại sao mỗi thiết lập quan trọng, và học các lỗi thường gặp để mã vạch của bạn hoạt động đáng tin cậy trong môi trường sản xuất.

Trong tutorial này bạn sẽ:

* Khởi tạo trình tạo Aspose.BarCode cho PDF417.
* Cấu hình số cột và hàng để kiểm soát hình dạng của mã vạch.
* Xuất kết quả dưới dạng ảnh PNG chất lượng cao.
* Khám phá các thiết lập tùy chọn cho việc sửa lỗi và độ dài dữ liệu.

Điều kiện duy nhất là có SDK .NET mới (.NET 6 trở lên) và giấy phép hoặc bản dùng thử miễn phí của **Aspose.BarCode for .NET**.

---

## Yêu cầu và cài đặt

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

| Yêu cầu | Lý do quan trọng |
|-------------|----------------|
| .NET 6 SDK hoặc mới hơn | Cung cấp môi trường chạy cho ứng dụng console C#. |
| Visual Studio 2022 (hoặc VS Code) | Cung cấp cho bạn một IDE với IntelliSense cho API Aspose. |
| Gói NuGet Aspose.BarCode cho .NET | Cung cấp `BarcodeGenerator`, `EncodeTypes`, và các trợ giúp xuất ảnh. |
| Quyền ghi vào thư mục đầu ra | Trình tạo sẽ ghi tệp PNG vào đĩa. |

Bạn có thể thêm gói NuGet bằng lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

---

## Bước 1: Tạo dự án console mới

Đầu tiên, tạo một ứng dụng console đơn giản sẽ chứa logic tạo mã vạch.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The full barcode generation flow is encapsulated in GeneratePdf417().
            GeneratePdf417();
            Console.WriteLine("Barcode image created successfully.");
        }

        // -----------------------------------------------------------------
        // Generates a PDF417 barcode with a custom layout and saves it as PNG.
        // -----------------------------------------------------------------
        static void GeneratePdf417()
        {
            // -------------------------------------------------------------
            // Step 2: Initialize the barcode generator for PDF417 with text.
            // -------------------------------------------------------------
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data for PDF417 barcode");

            // -------------------------------------------------------------
            // Step 3: Define a custom layout – set the number of columns and rows.
            // -------------------------------------------------------------
            generator.Parameters.Barcode.Pdf417.Columns = 4; // Controls horizontal density.
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // Controls vertical density.

            // Optional: increase error correction level for noisy environments.
            // Values: 0 (no correction) to 8 (maximum correction).
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // -------------------------------------------------------------
            // Step 4: Save the generated barcode as a PNG image.
            // -------------------------------------------------------------
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CustomPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### Tại sao đoạn mã này hoạt động

* **`BarcodeGenerator`** là điểm vào cho tất cả các loại mã vạch. Bằng cách truyền `EncodeTypes.Pdf417` bạn cho thư viện biết tạo ký hiệu PDF417.
* **Columns và rows** là các công cụ chính để điều chỉnh bố cục. Ít cột hơn tạo mã vạch cao hơn; nhiều cột hơn làm nó rộng hơn. Điều chỉnh các giá trị này để phù hợp với không gian hiển thị hình ảnh (ví dụ, máy in nhãn so với trang web).
* **Error correction** cải thiện độ tin cậy khi quét nếu mã vạch bị lem hoặc in trên vật liệu chất lượng thấp. Mức mặc định là 0; tăng lên một chút (2–4) là sự cân bằng tốt giữa kích thước và độ bền.
* **`Save`** ghi hình ảnh ra đĩa ở định dạng PNG, giúp giữ các cạnh sắc nét và hoạt động trên mọi trình duyệt và thiết bị di động.

Khi bạn chạy chương trình (`dotnet run`), nó sẽ tạo `CustomPdf417.png` trong thư mục dự án. PNG trông như sau:

![Generated PDF417 barcode image](https://example.com/images/pdf417-sample.png "Screenshot of generated barcode image created with PDF417 using C#")

*Alt text:* **tạo hình ảnh mã vạch** – Mã vạch PDF417 được tạo bằng C# và lưu dưới dạng PNG.

---

## Bước 2: Tinh chỉnh mã vạch cho các kịch bản thực tế

### Điều chỉnh độ dài dữ liệu

PDF417 có thể mã hoá tới 1.850 ký tự. Nếu bạn cần mã hoá chuỗi dài hơn, hãy cân nhắc chia dữ liệu thành nhiều mã vạch hoặc sử dụng **chế độ compact**:

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

Chế độ compact giảm số hàng nhưng có thể làm tăng mật độ hình ảnh, vì vậy hãy thử nghiệm với máy quét của bạn.

### Kiểm soát kích thước hình ảnh

Kích thước ảnh mặc định được tính dựa trên kích thước module (ô vuông nhỏ nhất trong mã vạch). Bạn có thể đặt DPI một cách rõ ràng hoặc thay đổi kích thước ảnh sau khi tạo:

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

Hoặc, sau khi lưu, bạn có thể thay đổi kích thước bằng System.Drawing nếu cần tạo thumbnail.

### Xử lý ký tự đặc biệt

PDF417 hỗ trợ toàn bộ bộ ký tự ASCII. Nếu dữ liệu của bạn chứa ký tự Unicode, hãy chắc chắn mã hoá chuỗi dưới dạng UTF‑8:

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## Bước 3: Các lỗi thường gặp và cách tránh

| Lỗi thường gặp | Triệu chứng | Cách khắc phục |
|---------|---------|-----|
| Quá nhiều cột cho dữ liệu đã cho | Mã vạch bị cắt ngắn hoặc ném ngoại lệ. | Giảm `Columns` hoặc để thư viện tự động kích thước bằng cách bỏ qua thiết lập. |
| Mức sửa lỗi thấp trên máy in nhiễu | Máy quét không đọc được mã vạch một cách không đều. | Tăng `ErrorCorrectionLevel` lên ít nhất 2. |
| Lưu vào thư mục chỉ đọc | `UnauthorizedAccessException` khi chạy. | Sử dụng thư mục có quyền ghi như `Environment.CurrentDirectory` hoặc `Path.GetTempPath()`. |
| Sử dụng phiên bản Aspose.BarCode cũ | Thiếu các thuộc tính như `CompactMode`. | Cập nhật gói NuGet lên phiên bản ổn định mới nhất. |

---

## Bước 4: Xác minh kết quả

Để xác nhận rằng mã vạch đã được tạo đúng, bạn có thể:

1. Mở `CustomPdf417.png` bằng bất kỳ trình xem ảnh nào – mã vạch nên rõ nét, với các mô-đun đen sắc nét trên nền trắng.
2. Sử dụng một ứng dụng quét PDF417 miễn phí (có trên iOS và Android) để quét hình ảnh. Ứng dụng sẽ hiển thị **“Sample data for PDF417 barcode”**.
3. (Tùy chọn) Tải hình ảnh trong một unit test bằng `System.Drawing.Bitmap` và kiểm tra rằng pixel tại `(0,0)` là màu đen, xác nhận rằng hình ảnh không rỗng.

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

Nếu kiểm tra thành công, bạn đã **tạo hình ảnh mã vạch** và **tạo mã vạch PDF417** một cách lập trình.

---

## Kết luận

Bạn giờ đã biết cách **tạo hình ảnh mã vạch** trong C# bằng cách **tạo mã vạch PDF417** với bố cục tùy chỉnh, điều chỉnh mức sửa lỗi và xuất ra PNG. Ví dụ hoàn chỉnh minh họa mọi bước cần thiết—from khởi tạo `BarcodeGenerator` đến lưu ảnh cuối cùng—để bạn có thể sao chép, dán và chạy trong dự án của mình.

Tiếp theo, bạn có thể khám phá:

* **Nhúng PNG vào một Web API** để khách hàng có thể yêu cầu mã vạch theo yêu cầu (`generate pdf417` như một dịch vụ).
* **Tạo hàng loạt** cho các bộ dữ liệu lớn—lặp qua danh sách chuỗi và lưu mỗi PNG vào cơ sở dữ liệu.
* **Định dạng đầu ra thay thế** (SVG, JPEG) bằng cách thay đổi `BarCodeImageFormat`.

Hãy tự do thử nghiệm với tỷ lệ cột/hàng, mức sửa lỗi và độ phân giải ảnh để đáp ứng chính xác yêu cầu của phần cứng máy quét hoặc thiết kế UI của bạn. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo hình ảnh mã vạch PDF417 trong C# – hướng dẫn đầy đủ](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [Cách tạo hình ảnh mã vạch PDF417 trong C# với tùy chọn Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Cách tạo mã vạch micro pdf417 và tạo PNG trong C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}