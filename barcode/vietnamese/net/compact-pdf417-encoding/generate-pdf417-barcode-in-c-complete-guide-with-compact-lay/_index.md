---
category: general
date: 2026-08-19
description: Tạo mã vạch PDF417 trong C# nhanh chóng. Tìm hiểu cách tạo mã vạch PDF417
  bằng C# sử dụng Aspose.BarCode với chế độ compact và các cài đặt tùy chỉnh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode c#
- Aspose.BarCode PDF417
- compact PDF417 barcode
- barcode X‑dimension
language: vi
lastmod: 2026-08-19
og_description: Tạo mã vạch PDF417 trong C# với Aspose.BarCode. Hướng dẫn này cho
  thấy cách tạo mã vạch PDF417 bằng C# ở chế độ compact, thiết lập kích thước X và
  lưu dưới dạng PNG.
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: Tạo mã vạch PDF417 trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  headline: Generate PDF417 barcode in C# – complete guide with compact layout
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    barcode C# using Aspose.BarCode with compact mode and custom settings.
  name: Generate PDF417 barcode in C# – complete guide with compact layout
  steps:
  - name: Why each line matters
    text: '* **`EncodeTypes.Pdf417`** – selects the PDF417 symbology, which supports
      up to ~1.1 KB of data. * **`XDimension.Pixels = 2`** – sets the basic bar width.
      Smaller values make the barcode thinner; larger values improve readability on
      low‑resolution devices. * **`Pdf417.Columns = 3`** – limits the num'
  - name: 4️⃣ Generate a high‑density PDF417 for printing
    text: 'If you need a barcode that fits on a small label, increase the column count
      and lower the X‑dimension:'
  - name: 5️⃣ Change the output format to SVG for vector scaling
    text: '```csharp generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
      ```'
  - name: 6️⃣ Encode binary data (e.g., a byte array)
    text: 'If you need to embed binary payloads, convert them to a Base64 string first:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Tạo mã vạch PDF417 trong C# – hướng dẫn đầy đủ với bố cục gọn
url: /vi/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide-with-compact-lay/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch PDF417 trong C# – hướng dẫn đầy đủ

Nếu bạn cần **generate PDF417 barcode** trong một ứng dụng .NET, hướng dẫn này sẽ cho bạn thấy cách thực hiện chính xác. Bạn sẽ thấy một ví dụ ngắn gọn, sẵn sàng cho môi trường sản xuất, tạo ra một mã vạch PDF417 dạng compact, tùy chỉnh X‑dimension, và lưu kết quả dưới dạng ảnh PNG.

Việc tạo PDF417 barcode thường gặp khi bạn phải mã hoá một lượng lớn dữ liệu—như thông tin vé, manifest vận chuyển, hoặc tài liệu nhận dạng—ở định dạng có thể đọc được bằng máy. Sử dụng Aspose.BarCode giúp quá trình trở nên đơn giản, và mã hoạt động với .NET 6+ hoặc .NET Framework 4.7.2 trở lên.

Trong hướng dẫn này bạn sẽ:

* Cài đặt gói NuGet Aspose.BarCode.
* Viết một chương trình C# tự chứa mà **generates PDF417 barcode** với số cột nhỏ và chế độ compact (truncated).
* Điều chỉnh độ rộng thanh (X‑dimension) để hiển thị sắc nét hơn.
* Lưu mã vạch dưới dạng file PNG.
* Khám phá các biến thể, trường hợp biên và các mẹo thực hành tốt nhất.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* Visual Studio 2022 (hoặc bất kỳ IDE C# nào) với .NET 6 SDK đã được cài đặt.
* Kết nối Internet để tải gói NuGet **Aspose.BarCode**.
* Quyền ghi vào thư mục nơi file PNG sẽ được lưu.

Không cần thư viện bổ sung; Aspose.BarCode xử lý việc mã hoá hình ảnh nội bộ.

## Bước 1: Thêm gói Aspose.BarCode

Mở dự án của bạn trong Visual Studio, nhấp chuột phải vào solution và chọn **Manage NuGet Packages**. Tìm kiếm `Aspose.BarCode` và cài đặt phiên bản ổn định mới nhất.

```bash
dotnet add package Aspose.BarCode
```

> **Pro tip:** Giữ gói luôn cập nhật. Các bản phát hành mới thường bao gồm cải thiện hiệu năng và hỗ trợ các runtime .NET mới nhất.

## Bước 2: Tạo ứng dụng console tối thiểu

Tạo một dự án console C# mới nếu bạn chưa có:

```bash
dotnet new console -n Pdf417Demo
cd Pdf417Demo
```

Thay thế nội dung của `Program.cs` bằng ví dụ đầy đủ dưới đây. Chương trình này minh họa **how to generate PDF417 barcode C#** từ đầu đến cuối.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -----------------------------------------------------------------
            // 1️⃣  Define the data you want to encode.
            // -----------------------------------------------------------------
            // The string can contain Unicode characters; Aspose.BarCode handles
            // encoding automatically. Here we use characters with diacritics to
            // prove Unicode support.
            string data = "Åspóse.Barcóde©";

            // -----------------------------------------------------------------
            // 2️⃣  Initialise the BarcodeGenerator for PDF417.
            // -----------------------------------------------------------------
            // EncodeTypes.Pdf417 tells the library which symbology to use.
            // The constructor also accepts the data to encode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // -----------------------------------------------------------------
            // 3️⃣  Configure visual parameters.
            // -----------------------------------------------------------------
            // • XDimension controls the bar width in pixels. A value of 2 gives
            //   a clear, readable barcode on most screens.
            // • Columns define how many data columns the barcode will use.
            //   Fewer columns produce a more compact image but increase the
            //   number of rows.
            // • Truncate enables “compact mode”, which removes the trailing
            //   stop pattern and reduces the overall size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // -----------------------------------------------------------------
            // 4️⃣  Choose the output format and save the image.
            // -----------------------------------------------------------------
            // BarCodeImageFormat.Png yields a lossless PNG file that works
            // well for web, print, and further image processing.
            string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### Tại sao mỗi dòng lại quan trọng

* **`EncodeTypes.Pdf417`** – chọn ký hiệu PDF417, hỗ trợ tới khoảng ~1.1 KB dữ liệu.
* **`XDimension.Pixels = 2`** – đặt độ rộng thanh cơ bản. Giá trị nhỏ hơn làm mã vạch mỏng hơn; giá trị lớn hơn cải thiện khả năng đọc trên thiết bị độ phân giải thấp.
* **`Pdf417.Columns = 3`** – giới hạn số cột, buộc trình tạo sử dụng nhiều hàng hơn, dẫn đến mã vạch cao hơn nhưng hẹp hơn.
* **`Pdf417.Truncate = true`** – kích hoạt chế độ compact, loại bỏ mẫu dừng và thu nhỏ hình ảnh mà không mất tính toàn vẹn dữ liệu.
* **`Save(..., BarCodeImageFormat.Png)`** – ghi file PNG. Bạn cũng có thể chọn `Jpeg`, `Bmp`, hoặc `Svg` tùy theo nhu cầu downstream.

Run the program:

```bash
dotnet run
```

Bạn sẽ thấy đầu ra console xác nhận vị trí file, và thư mục sẽ chứa `CompactPdf417.png`. Mở file PNG sẽ hiển thị một mã vạch PDF417 dạng compact, rõ ràng, mã hoá chuỗi Unicode.

## Bước 3: Xác minh mã vạch (tùy chọn nhưng được khuyến nghị)

Để đảm bảo mã vạch có thể đọc được, bạn có thể sử dụng bất kỳ ứng dụng scanner PDF417 tiêu chuẩn nào trên điện thoại thông minh hoặc thư viện giải mã trên máy tính để bàn. Văn bản đã mã hoá phải khớp chính xác với chuỗi `data` gốc, bao gồm cả các ký tự đặc biệt.

Nếu bạn gặp vấn đề giải mã:

* Tăng `XDimension` lên 3 hoặc 4 pixel.
* Giảm số cột (ví dụ, đặt `Columns = 2`).
* Vô hiệu hoá `Truncate` (`Truncate = false`) để thêm mẫu dừng.

Các điều chỉnh này đổi kích thước sang khả năng đọc, hữu ích cho máy in hoặc máy quét độ phân giải thấp.

## Bước 4: Khám phá các biến thể phổ biến

### 4️⃣ Tạo PDF417 mật độ cao cho việc in

Nếu bạn cần một mã vạch vừa vào nhãn nhỏ, tăng số cột và giảm X‑dimension:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 1;
generator.Parameters.Barcode.Pdf417.Columns = 6;
generator.Parameters.Barcode.Pdf417.Truncate = false; // keep full pattern
```

### 5️⃣ Thay đổi định dạng xuất ra SVG để mở rộng vector

Đầu ra SVG mở rộng mà không mất chất lượng, hoàn hảo cho các trang web đáp ứng.

```csharp
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

### 6️⃣ Mã hoá dữ liệu nhị phân (ví dụ, một mảng byte)

Nếu bạn cần nhúng tải trọng nhị phân, trước tiên chuyển chúng thành chuỗi Base64:

```csharp
byte[] payload = new byte[] { 0x01, 0xFF, 0xA5 };
string base64 = Convert.ToBase64String(payload);
generator = new BarcodeGenerator(EncodeTypes.Pdf417, base64);
```

Mã vạch bây giờ mang thông tin nhị phân, và bộ giải mã phải đảo ngược bước Base64.

## Câu hỏi thường gặp

| Question | Answer |
|----------|--------|
| **Có thể tạo PDF417 mà không dùng Aspose không?** | Có, có các thư viện khác như ZXing.Net hoặc Dynamsoft, nhưng Aspose.BarCode cung cấp kiểm soát bố cục phong phú hơn (cột, truncation) và xử lý Unicode tốt hơn. |
| **Độ dài dữ liệu tối đa là bao nhiêu?** | PDF417 có thể mã hoá tới 1.108 byte (≈ 1 KB) dữ liệu nhị phân. Nếu vượt quá, hãy cân nhắc chia dữ liệu thành nhiều mã vạch. |
| **Chế độ compact có tuân thủ tiêu chuẩn không?** | Truncated PDF417 là một phần của tiêu chuẩn ISO/IEC 15438 và được hỗ trợ rộng rãi, nhưng hãy xác minh rằng máy quét mục tiêu của bạn hỗ trợ rõ ràng chế độ này. |
| **Làm sao để thay đổi màu nền?** | Đặt `generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;` và `generator.Parameters.Barcode.ForeColor = System.Drawing.Color.Black;` trước khi lưu. |

## Kết luận

Bây giờ bạn đã biết **how to generate PDF417 barcode C#** bằng Aspose.BarCode, cách tinh chỉnh X‑dimension, bật chế độ compact, và xuất kết quả dưới dạng ảnh PNG. Ví dụ hoàn chỉnh, có thể chạy được có thể sao chép vào bất kỳ dự án .NET nào, và các biến thể được trình bày cho phép bạn điều chỉnh mã vạch cho các trường hợp in ấn, web, hoặc tải trọng nhị phân.

Bước tiếp theo bạn có thể khám phá:

* Tích hợp việc tạo mã vạch vào API ASP.NET Core trả về hình ảnh theo yêu cầu.
* Kết hợp PDF417 với mã QR trên cùng một nhãn để quét đa định dạng.
* Sử dụng lớp `Reader` của Aspose.BarCode để giải mã hình ảnh đã tạo và xác minh dữ liệu bằng chương trình.

Chúc lập trình vui vẻ, và tận hưởng sự linh hoạt mà các giải pháp **generate PDF417 barcode** mang lại cho ứng dụng của bạn!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ, hoạt động với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo Barcode – Compact PDF417 với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách tạo ảnh Barcode với tùy chỉnh không gian bổ sung bằng Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [Cách tạo barcode Aztec với tỷ lệ khung tùy chỉnh bằng Aspose.BarCode cho .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}