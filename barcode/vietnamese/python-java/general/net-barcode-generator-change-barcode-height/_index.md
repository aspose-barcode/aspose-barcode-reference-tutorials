---
category: general
date: 2026-07-18
description: Tìm hiểu cách tạo hình ảnh mã vạch bằng trình tạo mã vạch .net và dễ
  dàng thay đổi chiều cao mã vạch cho các ký hiệu GS1‑Databar Omni‑Directional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: vi
lastmod: 2026-07-18
og_description: Trình tạo mã vạch .net cho phép bạn nhanh chóng tạo hình ảnh mã vạch.
  Hướng dẫn này chỉ cách tạo mã vạch, điều chỉnh chiều cao thanh và lưu file PNG.
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: Thay đổi chiều cao mã vạch bằng trình tạo mã vạch .net
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET barcode generator – thay đổi chiều cao mã vạch
url: /vi/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – thay đổi chiều cao mã vạch

Bạn đã bao giờ tự hỏi **cách tạo mã vạch** mà không phải dùng hàng tá công cụ bên thứ ba chưa? Trong thế giới .NET có một cách khá gọn gàng để làm điều này, và thành phần then chốt là **.net barcode generator**. Chỉ với vài dòng C# bạn có thể tạo ra một ký hiệu GS1‑Databar Omni‑Directional, điều chỉnh chiều cao các thanh, và lưu kết quả thành file PNG.

Nếu bạn đang xây dựng một hệ thống quản lý tồn kho, máy in nhãn vận chuyển, hoặc bất kỳ ứng dụng nào cần mã có thể quét, hướng dẫn này sẽ đưa bạn từ không biết gì đến một mã vạch hoạt động trong vài phút. Chúng tôi sẽ đi qua toàn bộ mã, giải thích tại sao mỗi thiết lập quan trọng, và chỉ cho bạn cách **thay đổi chiều cao mã vạch** mà không vi phạm tiêu chuẩn.

## Những gì bạn cần

- .NET 6.0 hoặc mới hơn (API hoạt động tương tự trên .NET Framework 4.7+)
- Tham chiếu tới thư viện mã vạch (ví dụ, Aspose.BarCode for .NET – các lớp này được nhiều bộ công cụ thương mại sử dụng)
- Môi trường phát triển (Visual Studio, Rider, hoặc VS Code với phần mở rộng C#)
- Thư mục có quyền ghi – hướng dẫn sẽ lưu các file PNG vào đó

Chỉ vậy thôi. Không cần gói NuGet bổ sung nào ngoài thư viện mã vạch.

## Sử dụng .net barcode generator để thay đổi chiều cao mã vạch

Dưới đây là một **chương trình console đầy đủ, có thể chạy**. Dán nó vào một dự án C# mới, điều chỉnh thư mục đầu ra, và nhấn F5.

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### Tại sao mỗi dòng lại quan trọng

| Line | Reason |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | Khởi tạo **.net barcode generator** với ký hiệu và dữ liệu mong muốn. Enum `EncodeTypes.DatabarOmniDirectional` cho thư viện biết sử dụng định dạng GS1‑Databar Omni‑Directional. |
| `XDimension.Pixels = 2;` | X‑dimension là độ rộng của thanh mỏng nhất. Đặt nó thành *2 pixel* tạo hình ảnh sắc nét trên hầu hết màn hình đồng thời giữ kích thước file nhỏ. |
| `BarHeight.Pixels = 30;` | Đây là bước **thay đổi chiều cao mã vạch** xác định độ cao của mỗi thanh. Chiều cao 30 pixel là mặc định tốt cho nhãn nhỏ. |
| `generator.Save(...);` | Lưu mã vạch vào file PNG. PNG không mất dữ liệu, có nghĩa là máy quét sẽ thấy đúng mẫu bạn tạo. |
| `BarHeight.Pixels = 60;` | Ở đây chúng ta **thay đổi chiều cao mã vạch** một lần nữa—lần này thành 60 pixel. Thư viện sẽ tự động vẽ lại ký hiệu với kích thước mới khi bạn gọi `Save` lần thứ hai. |
| `Console.WriteLine(...);` | Cung cấp phản hồi nhanh rằng quá trình đã hoàn thành mà không ném ngoại lệ. |

> **Mẹo chuyên nghiệp:** Nếu bạn cần đầu ra độ phân giải cao hơn cho việc in, chuyển `BarCodeImageFormat.Png` sang `BarCodeImageFormat.Tiff` và tăng thuộc tính `Resolution` (ví dụ, `generator.Parameters.ImageResolution = 300;`). Chiều cao thanh vẫn được giữ, chỉ được vẽ ở DPI mịn hơn.

## Cách tạo ảnh mã vạch với các thiết lập khác nhau

Đoạn mã trên bao quát các kiến thức cơ bản, nhưng trong thực tế thường cần các điều chỉnh bổ sung:

### Điều chỉnh X‑dimension cho bản in lớn hơn
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
Tăng X‑dimension làm toàn bộ mã vạch lớn hơn mà không thay đổi dữ liệu đã mã hoá. Điều này hữu ích khi bạn in trên nhãn lớn.

### Chuyển đổi định dạng đầu ra
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG có thể phóng to vô hạn, rất phù hợp cho các máy quét dựa trên web cần vector sắc nét.

### Thêm văn bản có thể đọc được bởi con người
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
Bật `CodeTextVisible` sẽ thêm dữ liệu thô dưới mã vạch, hữu ích cho việc kiểm tra trong quá trình thử nghiệm.

## Những lỗi thường gặp khi bạn **thay đổi chiều cao mã vạch**

1. **Chiều cao quá nhỏ** – Một số máy quét yêu cầu chiều cao thanh tối thiểu (thường là 10 mm trong đơn vị vật lý). Nếu bạn đặt `BarHeight.Pixels` quá thấp, ảnh tạo ra có thể không đọc được trên máy quét thực tế. Luôn kiểm tra với phần cứng mục tiêu.
2. **X‑dimension và chiều cao không phù hợp** – Chiều cao thanh quá lớn kết hợp với X‑dimension quá nhỏ có thể trông bị kéo dài và gây lỗi giải mã. Hãy nhắm tới tỉ lệ cân bằng (khoảng 3:1 đến 5:1) trừ khi tiêu chuẩn quy định khác.
3. **Quên đặt lại tham số** – Trình tạo giữ trạng thái giữa các lần lưu. Nếu bạn thay đổi `BarHeight` cho một ảnh và sau đó dùng lại cùng một instance cho mã vạch khác, chiều cao trước sẽ vẫn còn. Hãy đặt lại thuộc tính hoặc khởi tạo một `BarcodeGenerator` mới cho mỗi mã vạch riêng biệt.

## Ví dụ toàn diện từ đầu đến cuối (kèm cài đặt NuGet)

Nếu bạn bắt đầu từ đầu, hãy làm theo các bước sau để dự án chạy được:

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

Thay thế `Program.cs` được tạo tự động bằng khối mã đã hiển thị ở trên, **nhớ thay `YOUR_DIRECTORY`** bằng một đường dẫn như `Path.Combine(Environment.CurrentDirectory, "output")`. Sau đó:

```bash
dotnet run
```

Bạn sẽ thấy hai file PNG trong thư mục `output`:

- `DatabarBarHeight30Pixels.png` – mã vạch cao 30 pixel gọn gàng.
- `DatabarBarHeight60Pixels.png` – phiên bản cao 60 pixel hơn.

Cả hai ảnh sẽ trông tương tự, nhưng ảnh thứ hai có các thanh dài hơn đáng kể, giúp các máy quét độ phân giải thấp dễ đọc hơn.

![Ví dụ chiều cao mã vạch](/images/barcode-height.png){alt=".net barcode generator output hiển thị các chiều cao thanh khác nhau"}

## Tóm tắt & các bước tiếp theo

Chúng tôi đã trình bày cách **tạo ảnh mã vạch** bằng **.net barcode generator**, tinh chỉnh thuộc tính **thay đổi chiều cao mã vạch**, và lưu kết quả ở định dạng PNG. Những điểm chính cần nhớ là:

- Khởi tạo trình tạo với `EncodeTypes` phù hợp.
- Kiểm soát kích thước hiển thị bằng `XDimension` và `BarHeight`.
- Gọi `Save` sau mỗi lần thay đổi để lưu ảnh mới.
- Điều chỉnh độ phân giải, định dạng,

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch Aztec với tỷ lệ khung tùy chỉnh bằng Aspose.BarCode cho .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cách tạo dotcode với văn bản mở rộng bằng Aspose.BarCode cho .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Cách tạo mã DataMatrix (ECC 200) bằng Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}