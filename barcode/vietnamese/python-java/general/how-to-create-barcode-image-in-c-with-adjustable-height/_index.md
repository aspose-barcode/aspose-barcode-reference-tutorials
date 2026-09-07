---
category: general
date: 2026-09-07
description: Tìm hiểu cách tạo hình ảnh mã vạch trong C# và điều chỉnh chiều cao,
  chiều rộng và định dạng để nhanh chóng tạo các tệp PNG mã vạch.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: vi
lastmod: 2026-09-07
og_description: Tạo hình ảnh mã vạch trong C# và học cách đặt kích thước mã vạch,
  thay đổi chiều cao mã vạch, và tạo file PNG mã vạch cho bất kỳ ứng dụng nào.
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: Tạo hình ảnh mã vạch trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: Cách tạo hình ảnh mã vạch trong C# với chiều cao có thể điều chỉnh
url: /vi/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo ảnh mã vạch trong C# với chiều cao có thể điều chỉnh

Nếu bạn cần tạo ảnh mã vạch trong C# cho hệ thống điểm bán hàng hoặc phần mềm quản lý tồn kho, hướng dẫn này sẽ chỉ cho bạn quy trình hoàn chỉnh. Bạn sẽ thấy cách thiết lập các tham số mã vạch, thay đổi chiều cao mã vạch và tạo các tệp PNG đáp ứng yêu cầu về hình ảnh.

Việc tạo ảnh mã vạch là một nhiệm vụ phổ biến khi tích hợp phần cứng quét, in nhãn, hoặc xây dựng bảng điều khiển báo cáo. Khi kết thúc tutorial này, bạn sẽ có một đoạn mã có thể tái sử dụng cho phép điều chỉnh **X‑dimension**, chiều cao và định dạng đầu ra của mã vạch mà không rời khỏi IDE.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 (hoặc mới hơn) đã được cài đặt – mã sẽ biên dịch với bất kỳ SDK .NET nào hiện đại.
* Tham chiếu tới thư viện **Aspose.BarCode** (có sẵn qua NuGet `Aspose.BarCode`).
* Kiến thức cơ bản về ứng dụng console C#.

Những yêu cầu này đảm bảo ví dụ chạy ngay trên Windows, Linux hoặc macOS.

## Bước 1: Thiết lập dự án và nhập thư viện

Tạo một dự án console mới và thêm gói barcode:

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Bây giờ mở *Program.cs* và thêm các chỉ thị `using` cần thiết:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

Các import này cho phép bạn truy cập `BarcodeGenerator`, `EncodeTypes` và các enum định dạng ảnh cần thiết để **tạo ảnh mã vạch**.

## Bước 2: Khởi tạo generator với loại mã vạch mong muốn

Dòng code đầu tiên tạo một `BarcodeGenerator` biết loại mã vạch nào sẽ được mã hoá. Trong ví dụ này chúng ta sử dụng symbology DataBar Omni‑Directional, nhưng bạn có thể thay `EncodeTypes.DatabarOmniDirectional` bằng bất kỳ loại nào khác được Aspose.BarCode hỗ trợ.

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Chuỗi `"(01)12345678901231"` tuân theo định dạng GS1 Application Identifier, mà nhiều nhà bán lẻ yêu cầu. Khởi tạo generator là nền tảng cho mọi thao tác **cách thiết lập mã vạch** tiếp theo.

## Bước 3: Cách thiết lập kích thước mã vạch – X‑dimension và chiều cao

### 3.1 Điều chỉnh độ rộng thanh mỏng (X‑dimension)

X‑dimension kiểm soát độ dày của thanh mỏng nhất. Giá trị **2 pixel** tạo ra vẻ mịn hơn, hữu ích khi bạn cần nhãn gọn.

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 Thay đổi chiều cao mã vạch để cân bằng hình ảnh

Chiều cao thanh quyết định mã vạch cao bao nhiêu. Dưới đây chúng ta hiển thị hai chiều cao phổ biến—30 pixel cho nhãn nhỏ và 60 pixel cho nhãn lớn hơn. Điều này minh họa **cách điều chỉnh chiều cao mã vạch** một cách lập trình.

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## Bước 4: Tạo các tệp PNG mã vạch với chiều cao khác nhau

### 4.1 Lưu ảnh đầu tiên (chiều cao 30 px)

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 Tăng chiều cao và lưu ảnh thứ hai

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Hai lệnh `Save` này minh họa **tạo PNG mã vạch** với các kích thước khác nhau trong khi tái sử dụng cùng một instance của generator. Định dạng ảnh được đặt rõ ràng là PNG, giữ nguyên chất lượng lossless—lý tưởng cho việc in ấn hoặc hiển thị trên màn hình.

## Bước 5: Ví dụ đầy đủ, có thể chạy ngay

Kết hợp tất cả lại sẽ cho ra một phương thức `Main` duy nhất mà bạn có thể sao chép vào bất kỳ dự án console C# nào:

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

Chạy chương trình này sẽ tạo hai tệp PNG trong thư mục output của dự án:

* `DatabarBarHeight30Pixels.png` – mã vạch gọn 30 px.
* `DatabarBarHeight60Pixels.png` – mã vạch lớn 60 px.

Cả hai tệp đều chứa **ảnh mã vạch được tạo** có thể nhúng vào HTML, in lên nhãn, hoặc gửi tới ứng dụng di động để quét.

## Các câu hỏi thường gặp và xử lý các trường hợp đặc biệt

| Câu hỏi | Trả lời |
|----------|--------|
| **Nếu tôi cần định dạng ảnh khác?** | Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg`, `Bmp` hoặc `Gif`. Thư viện sẽ tự động xử lý chuyển đổi. |
| **Có thể thay đổi màu nền/màu chữ không?** | Có. Sử dụng `generator.Parameters.Barcode.ForeColor` và `BackColor` để đặt giá trị `System.Drawing.Color` trước khi gọi `Save`. |
| **Cách tạo mã vạch mà không lưu vào đĩa?** | Gọi `generator.GenerateBarCodeImage()` để nhận đối tượng `System.Drawing.Image`, sau đó stream trực tiếp tới response hoặc database. |
| **Nếu chuỗi dữ liệu vượt quá giới hạn của symbology?** | Generator sẽ ném `ArgumentException`. Hãy kiểm tra độ dài đầu vào hoặc cắt ngắn theo đặc tả của symbology. |
| **Có cách xử lý hàng loạt nhiều mã vạch không?** | Đặt các bước trong một vòng `foreach` cập nhật `generator.CodeText` và `BarHeight` cho mỗi mục, rồi gọi `Save` với tên tệp duy nhất. |

Xử lý các kịch bản này giúp tutorial **cách điều chỉnh mã vạch** trở nên vững chắc cho các dự án thực tế.

## Mẹo chuyên nghiệp để tạo mã vạch đáng tin cậy

* **Cache generator** khi bạn tạo nhiều mã vạch cùng loại; tái sử dụng đối tượng giảm tải cấp phát bộ nhớ.
* **Đặt `Resolution`** (`generator.Parameters.ImageResolution.Dpi`) nếu bạn cần PNG độ phân giải cao cho việc in.
* **Xác thực dữ liệu GS1** trước khi gán cho `CodeText` để tránh lỗi mã hoá gây lỗi quét.
* **Kiểm tra trên máy quét thực tế** sau khi thay đổi chiều cao hoặc X‑dimension—một số thiết bị cũ có yêu cầu kích thước tối thiểu.

## Kết luận

Bây giờ bạn đã biết cách **tạo ảnh mã vạch** trong C#, **cách thiết lập kích thước mã vạch**, **cách điều chỉnh chiều cao mã vạch**, và **tạo PNG mã vạch** cho bất kỳ yêu cầu hình ảnh nào. Bằng cách tinh chỉnh `XDimension` và `BarHeight` bạn có thể tạo mã vạch gọn hoặc lớn mà không cần thay đổi dữ liệu gốc.

Tiếp theo, hãy khám phá các chủ đề liên quan như **thay đổi chiều cao mã vạch** động dựa trên đầu vào người dùng, nhúng mã vạch vào báo cáo PDF bằng Aspose.PDF, hoặc chuyển sang tạo QR‑code với `EncodeTypes.QR`. Thử nghiệm với các symbology và định dạng xuất khác nhau để thành thạo việc tạo mã vạch trong C#.

## Bạn Nên Học Gì Tiếp Theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ code hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Create GS1 Barcode Images in C# – How to Generate Barcode C# Quickly](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}