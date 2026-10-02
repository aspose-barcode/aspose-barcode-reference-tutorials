---
category: general
date: 2026-10-02
description: Tạo mã vạch từ văn bản trong C# bằng Aspose.BarCode. Tìm hiểu cách tạo
  mã vạch PDF417 và xem cách tạo mã vạch PDF417 ở chế độ compact.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: vi
lastmod: 2026-10-02
og_description: Tạo mã vạch từ văn bản trong C# với Aspose.BarCode. Hướng dẫn này
  chỉ cách tạo mã vạch PDF417 và cách tạo mã vạch PDF417 ở chế độ compact.
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: Tạo mã vạch từ văn bản trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Cách tạo mã vạch từ văn bản trong C# với Aspose.BarCode
url: /vi/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch từ văn bản trong C# với Aspose.BarCode

Nếu bạn cần **tạo mã vạch từ văn bản** trong một ứng dụng .NET, hướng dẫn này sẽ dẫn bạn qua toàn bộ quá trình. Bạn sẽ thấy một ví dụ sẵn sàng chạy mà **tạo mã vạch PDF417** và cũng trả lời **cách tạo mã vạch PDF417** trong bố cục gọn.

Việc tạo mã vạch bằng chương trình loại bỏ các bước thủ công và đảm bảo tính nhất quán trên mọi tài liệu. Khi kết thúc hướng dẫn này, bạn sẽ có một tệp PNG chứa mã vạch PDF417 mà bạn có thể nhúng vào hoá đơn, vé, hoặc thẻ căn cước.

## Những gì bạn cần

- .NET 6.0 SDK hoặc phiên bản mới hơn (mã cũng hoạt động với .NET Framework 4.7.2+)
- Visual Studio 2022 hoặc bất kỳ trình soạn thảo nào hỗ trợ C#
- Giấy phép NuGet cho **Aspose.BarCode for .NET** (bản dùng thử miễn phí đủ cho việc thử nghiệm)

> **Mẹo chuyên nghiệp:** Thêm gói NuGet qua CLI để giữ dự án sạch sẽ:  
> `dotnet add package Aspose.BarCode`

## Bước 1: Thiết lập dự án console

Tạo một ứng dụng console mới và tham chiếu thư viện Aspose.BarCode.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Lệnh `dotnet new console` tạo ra một tệp `Program.cs` mà chúng ta sẽ thay thế bằng ví dụ đầy đủ bên dưới.

## Bước 2: Cách tạo mã vạch từ văn bản – mã cốt lõi

Mở `Program.cs` và thay thế nội dung của nó bằng đoạn mã sau. Mỗi dòng đều có chú thích để giải thích lý do tồn tại.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Tại sao mỗi thiết lập lại quan trọng

| Thiết lập | Mục đích |
|--------|----------|
| `EncodeTypes.Pdf417` | Chọn ký hiệu PDF417, có thể lưu trữ lượng lớn dữ liệu trong ma trận hai chiều. |
| `XDimension.Pixels = 2` | Điều khiển độ rộng của mỗi mô-đun; giá trị 2 pixel cân bằng giữa khả năng đọc và kích thước tệp. |
| `Pdf417.Columns = 3` | Giảm số cột, làm cho mã vạch gọn hơn mà không mất dữ liệu. |
| `Pdf417.Truncate = true` | Kích hoạt chế độ gọn, loại bỏ phần đệm không cần thiết và rút ngắn mã vạch. |
| `BarCodeImageFormat.Png` | PNG giữ chất lượng không mất dữ liệu, lý tưởng cho xử lý hoặc in ấn tiếp theo. |

## Bước 3: Tạo mã vạch PDF417 – chạy ví dụ

Xây dựng và chạy dự án:

```bash
dotnet run
```

Khi thực thi hoàn thành, bạn sẽ thấy:

```
Barcode saved to CompactPdf417.png
```

Mở `CompactPdf417.png` để xem kết quả. Hình ảnh chứa một mã vạch PDF417 mã hoá chuỗi **Åspóse.Barcóde©**.

![Create barcode from text example](barcode-example.png)

*Alt text: tạo mã vạch từ văn bản – mã vạch PDF417 được lưu dưới dạng PNG*

## Bước 4: Cách tạo mã vạch PDF417 với mức sửa lỗi tùy chỉnh (tùy chọn)

Nếu môi trường quét của bạn có nhiều nhiễu, bạn có thể tăng mức sửa lỗi:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

Tăng mức sửa lỗi sẽ làm mã vạch lớn hơn nhưng cải thiện khả năng chịu lỗi khi bị hư hỏng.

## Bước 5: Những lỗi thường gặp và xử lý trường hợp đặc biệt

1. **Ký tự không hợp lệ** – PDF417 hỗ trợ Unicode, nhưng một số máy quét cũ có thể từ chối các ký tự không phải ASCII. Hãy thử nghiệm với phần cứng mục tiêu của bạn.
2. **Quyền truy cập đường dẫn tệp** – Đảm bảo thư mục bạn ghi vào có quyền ghi; nếu không `Save` sẽ ném `UnauthorizedAccessException`.
3. **Kích thước hình ảnh** – Giá trị `XDimension` quá cao tạo ra các tệp PNG lớn. Giữ kích thước pixel trong khoảng 1 đến 4 cho hầu hết các kịch bản hiển thị trên màn hình.

## Tóm tắt

Bây giờ bạn đã biết cách **tạo mã vạch từ văn bản** trong C# bằng Aspose.BarCode, cách **tạo mã vạch PDF417** với bố cục gọn, và các bước chính xác để **cách tạo mã vạch PDF417** với các thiết lập tùy chỉnh. Mã hoàn chỉnh, có thể chạy được ở trên có thể sao chép vào bất kỳ dự án .NET nào và điều chỉnh cho các đầu vào văn bản hoặc định dạng đầu ra khác nhau (ví dụ: JPEG, BMP).

## Các bước tiếp theo

- Khám phá các ký hiệu khác như QR Code hoặc Code128 bằng cách thay đổi `EncodeTypes`.
- Tích hợp PNG đã tạo vào PDF bằng Aspose.PDF để tạo tài liệu đầu‑cuối.
- Thử nghiệm với `generator.Parameters.Barcode.Pdf417.Rows` để điều khiển mật độ dọc.

Bạn có thể tự do chỉnh sửa ví dụ, nhúng mã vạch vào ứng dụng của mình, và chia sẻ kết quả với cộng đồng. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ hoạt động cùng giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch PDF417 trong C# – ví dụ gọn](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [Cách tạo mã vạch PDF417 trong C# với chế độ gọn](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Cách tạo mã vạch PDF417 trong C# – hướng dẫn từng bước](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}