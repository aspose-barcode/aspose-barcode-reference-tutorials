---
category: general
date: 2026-09-13
description: Tìm hiểu cách tạo mã vạch trong C#, tùy chỉnh kích thước mã vạch và lưu
  hình ảnh mã vạch dưới dạng PNG bằng Aspose.BarCode. Hướng dẫn chi tiết từng bước.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: vi
lastmod: 2026-09-13
og_description: Cách tạo mã vạch trong C# với kích thước mã vạch tùy chỉnh và lưu
  hình ảnh mã vạch dưới dạng PNG. Theo dõi hướng dẫn đầy đủ này cho Aspose.BarCode.
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: Cách tạo mã vạch, đặt kích thước tùy chỉnh và lưu hình ảnh trong C#
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Cách tạo mã vạch, đặt kích thước tùy chỉnh và lưu hình ảnh trong C#
url: /vi/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch với kích thước tùy chỉnh và lưu hình ảnh trong C#

Nếu bạn cần **cách tạo mã vạch** trong một ứng dụng .NET, hướng dẫn này sẽ cho bạn một giải pháp hoàn chỉnh. Bạn sẽ thấy cách điều chỉnh **kích thước mã vạch tùy chỉnh** và **lưu hình ảnh mã vạch** chỉ với vài dòng mã C#.

Việc tạo mã vạch là yêu cầu phổ biến cho các hệ thống quản lý tồn kho, nhãn vận chuyển và ứng dụng điểm bán hàng. Khi kết thúc hướng dẫn này, bạn sẽ có một chương trình có thể chạy được tạo ra hai mã DataBar‑Stacked‑Omnidirectional, mỗi mã có tỷ lệ khung hình khác nhau, và ghi chúng vào các tệp PNG trên đĩa.

**Yêu cầu trước**

- .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+)
- Visual Studio 2022 hoặc bất kỳ IDE C# nào
- Aspose.BarCode cho .NET (bản dùng thử miễn phí hoặc gói NuGet có bản quyền)

---

## Cách tạo mã vạch với Aspose.BarCode

Thư viện Aspose.BarCode trừu tượng hoá các chi tiết mức thấp của các tiêu chuẩn mã vạch, cho phép bạn tập trung vào dữ liệu cần mã hoá và giao diện trực quan mà bạn cần.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### Tại sao mỗi dòng lại quan trọng

| Bước | Giải thích |
|------|------------|
| **1️⃣ Tạo bộ sinh** | Enum `EncodeTypes.DatabarStackedOmniDirectional` cho Aspose biết nên sử dụng ký hiệu mã vạch nào. Chuỗi `"(01)12345678901231"` tuân theo định dạng dữ liệu GS1‑128, trong đó `(01)` là Application Identifier cho GTIN. |
| **2️⃣ Đặt X‑dimension** | `XDimension.Pixels` xác định độ rộng của một mô-đun mã vạch duy nhất (vạch nhỏ nhất). Thay đổi giá trị này là cách chính để đạt được **kích thước mã vạch tùy chỉnh** mà không thay đổi dữ liệu đã mã hoá. |
| **3️⃣ Đặt tỷ lệ khung hình & lưu** | `DataBar.AspectRatio` điều khiển tỷ lệ chiều cao‑so‑với‑chiều rộng của các ký hiệu DataBar. Tỷ lệ 15 tạo ra mã vạch tương đối ngắn và rộng, trong khi 30 làm nó cao hơn. `Save` ghi biểu diễn trực quan vào tệp PNG, đáp ứng yêu cầu **lưu hình ảnh mã vạch**. |
| **4️⃣ Thay đổi tỷ lệ khung hình & lưu lại** | Việc tái sử dụng cùng một thể hiện của bộ sinh cho phép bạn tạo ra nhiều hình ảnh với các đặc điểm trực quan khác nhau trong khi dữ liệu vẫn không đổi. |

---

## Điều chỉnh kích thước mã vạch tùy chỉnh vượt qua X‑dimension

Trong khi `XDimension.Pixels` đặt độ rộng mô-đun, bạn cũng có thể tinh chỉnh tổng kích thước của mã vạch bằng cách kết hợp hai thuộc tính:

1. **`BarHeight`** – chiều cao cụ thể tính bằng pixel.  
2. **`BarWidth`** – chiều rộng cụ thể tính bằng pixel (ghi đè X‑dimension).

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **Mẹo chuyên nghiệp:** Khi in mã vạch, luôn kiểm tra hình ảnh đã tạo ở kích thước in cuối cùng. Độ rộng mô-đun 2 px phù hợp cho hiển thị trên màn hình, nhưng nhãn in thường cần ít nhất 4 px để vẫn có thể quét được.

---

## Lựa chọn định dạng hình ảnh phù hợp để lưu hình ảnh mã vạch

Aspose.BarCode hỗ trợ PNG, JPEG, BMP, GIF và TIFF. PNG là định dạng không mất dữ liệu và giữ các cạnh sắc nét, là lựa chọn an toàn nhất cho hầu hết các ứng dụng. Nếu bạn cần tệp nhỏ hơn cho web, JPEG với thiết lập chất lượng 90 hoạt động tốt, nhưng hãy lưu ý rằng các artefact nén có thể ảnh hưởng đến độ tin cậy khi quét.

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## Ví dụ đầy đủ, có thể chạy

Dưới đây là một ứng dụng console tự chứa mà bạn có thể sao chép, dán và chạy. Nó minh họa **cách tạo mã vạch**, chỉnh sửa **kích thước mã vạch tùy chỉnh**, và **lưu hình ảnh mã vạch** ở hai định dạng khác nhau.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**Kết quả mong đợi trên console**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

Bốn tệp hình ảnh sẽ xuất hiện trong chương trình

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ với các giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã DataMatrix bằng Aspose.BarCode cho .NET – Hướng dẫn từng bước](/barcode/english/net/datamatrix-barcode-configuration/)
- [Cách tạo mã PDF417 với Aspose – Hướng dẫn đầy đủ](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Cách tạo mã Aztec với tỷ lệ khung hình tùy chỉnh bằng Aspose.BarCode cho .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}