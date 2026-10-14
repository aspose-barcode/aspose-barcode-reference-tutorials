---
category: general
date: 2026-09-29
description: Tìm hiểu cách tạo mã vạch Databar đa hướng trong C# với Aspose.BarCode.
  Điều chỉnh kích thước X, đặt tỷ lệ khung hình và lưu ảnh PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional databar barcode
- DataBar stacked omnidirectional barcode
- set barcode aspect ratio
- Aspose.BarCode C#
- generate barcode image
language: vi
lastmod: 2026-09-29
og_description: Tạo mã vạch Databar đa hướng trong C# bằng Aspose.BarCode. Học cách
  đặt kích thước X, điều chỉnh tỷ lệ khung hình và xuất file PNG.
og_image_alt: Screenshot showing two PNG files of an omnidirectional Databar barcode
  with different aspect ratios
og_title: Tạo mã vạch Databar đa hướng trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  headline: How to create omnidirectional Databar barcode in C#
  type: TechArticle
- description: Learn how to create omnidirectional Databar barcode in C# with Aspose.BarCode.
    Adjust X‑dimension, set aspect ratio, and save PNG images.
  name: How to create omnidirectional Databar barcode in C#
  steps:
  - name: What if I need a different X‑dimension?
    text: You can assign any integer value to `XDimension.Pixels`. Values below `1`
      are ignored, and values above `10` may produce oversized modules that exceed
      printer margins. Test the visual output after each change.
  - name: How do I encode other AI‑generated data (e.g., UPC, EAN)?
    text: Replace the data string in the `BarcodeGenerator` constructor with the appropriate
      Application Identifier (AI). For a UPC‑A code, use `"012345678905"` without
      an AI prefix.
  - name: Can I export to formats other than PNG?
    text: Yes. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`,
      `BarCodeImageFormat.Tiff`, and `BarCodeImageFormat.Bmp`. Choose the format that
      matches your downstream workflow.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cách tạo mã vạch Databar đa hướng trong C#
url: /vi/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch Databar đa hướng trong C#

Nếu bạn cần **tạo mã vạch Databar đa hướng** trong một ứng dụng .NET, hướng dẫn này sẽ cho bạn các bước chính xác. Bạn sẽ thấy cách khởi tạo một mã vạch DataBar stacked omnidirectional, cấu hình kích thước X‑dimension, thay đổi tỷ lệ khung hình, và tạo ảnh PNG bằng Aspose.BarCode.

Việc tạo **DataBar stacked omnidirectional barcode** là phổ biến khi bạn phải mã hoá các định danh sản phẩm cho máy quét bán lẻ. Trong tutorial này bạn sẽ học cách **đặt tỷ lệ khung hình của mã vạch**, kiểm soát kích thước mô-đun, và xuất kết quả mà không rời khỏi IDE.

## Prerequisites

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

- .NET 6.0 hoặc mới hơn đã được cài đặt
- Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ C#)
- Gói NuGet **Aspose.BarCode for .NET** (phiên bản 23.12 hoặc mới hơn)

Bạn có thể thêm gói này qua NuGet Package Manager:

```bash
dotnet add package Aspose.BarCode
```

## Step 1: Initialise the omnidirectional Databar barcode

Bước đầu tiên là tạo một đối tượng `BarcodeGenerator` nhắm tới ký hiệu **DataBar stacked omnidirectional**. Hàm khởi tạo nhận loại mã hoá và chuỗi dữ liệu.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialise a DataBar stacked omnidirectional barcode with GTIN data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

**Tại sao điều này quan trọng:** Giá trị `EncodeTypes.DatabarStackedOmniDirectional` thông báo cho Aspose.BarCode render định dạng Databar đa hướng cụ thể, cần thiết để quét ở cả hai hướng.

## Step 2: Define the X‑dimension (module size)

X‑dimension kiểm soát độ rộng của một mô-đun mã vạch tính bằng pixel. Giá trị `2` pixel thường phù hợp cho việc hiển thị trên màn hình và hầu hết máy in.

```csharp
        // Set the basic size of the barcode modules (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tại sao điều này quan trọng:** Một X‑dimension đồng nhất đảm bảo mã vạch đáp ứng các yêu cầu kích thước tối thiểu cho máy quét bán lẻ đồng thời giữ kích thước tệp ảnh ở mức hợp lý.

## Step 3: Set the first aspect ratio and save the image

**Tỷ lệ khung hình** xác định mối quan hệ chiều cao‑với‑chiều rộng của DataBar. Tỷ lệ `15` tạo ra một mã vạch cao, hẹp lý tưởng cho không gian nhãn dày hẹp.

```csharp
        // Apply aspect ratio 15 and save the first PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

**Tại sao điều này quan trọng:** Điều chỉnh tỷ lệ khung hình cho phép bạn đặt mã vạch vào các bố cục nhãn khác nhau mà không làm giảm khả năng đọc. PNG đã lưu có thể xem bằng bất kỳ trình xem ảnh nào.

## Step 4: Change the aspect ratio and generate a second image

Đôi khi cần một mã vạch rộng hơn — ví dụ khi nhãn có không gian ngang lớn hơn. Thay đổi tỷ lệ thành `30` tạo ra một hình dạng phẳng hơn.

```csharp
        // Change aspect ratio to 30 and save a second PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
    }
}
```

**Tại sao điều này quan trọng:** Bằng cách khai thác thuộc tính **set barcode aspect ratio**, bạn có thể tạo ra nhiều biến thể mã vạch từ cùng một đoạn code, đơn giản hoá quy trình tạo nhãn tự động.

## Expected output

Chạy chương trình sẽ tạo ra hai tệp PNG trong thư mục output của ứng dụng:

| Tên tệp                     | Tỷ lệ khung hình | Mô tả trực quan                                            |
|-----------------------------|------------------|------------------------------------------------------------|
| `DatabarAspectRatio15.png`  | 15               | Mã vạch cao, hẹp thích hợp cho các nhãn hẹp                |
| `DatabarAspectRatio30.png`  | 30               | Mã vạch rộng hơn, chiếm nhiều không gian ngang hơn         |

Bạn có thể nhúng các ảnh này vào báo cáo, in lên bao bì sản phẩm, hoặc gửi tới dịch vụ web để xử lý tiếp.

![Ví dụ tạo mã vạch Databar đa hướng](databar-example.png "Ví dụ tạo mã vạch Databar đa hướng")

*Ảnh chụp màn hình hiển thị hai tệp PNG đã tạo cạnh nhau.*

## Common questions and edge cases

### Nếu tôi cần một X‑dimension khác?

Bạn có thể gán bất kỳ giá trị nguyên nào cho `XDimension.Pixels`. Giá trị dưới `1` sẽ bị bỏ qua, và giá trị trên `10` có thể tạo ra các mô-đun quá lớn, vượt quá lề máy in. Hãy kiểm tra kết quả hình ảnh sau mỗi thay đổi.

### Làm thế nào để mã hoá dữ liệu AI khác (ví dụ: UPC, EAN)?

Thay chuỗi dữ liệu trong hàm khởi tạo `BarcodeGenerator` bằng Application Identifier (AI) phù hợp. Đối với mã UPC‑A, sử dụng `"012345678905"` mà không cần tiền tố AI.

### Tôi có thể xuất ra các định dạng khác ngoài PNG không?

Có. Phương thức `Save` chấp nhận `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Gif`, `BarCodeImageFormat.Tiff`, và `BarCodeImageFormat.Bmp`. Chọn định dạng phù hợp với quy trình downstream của bạn.

## Pro tip: reuse the generator for batch processing

Nếu bạn cần tạo hàng chục mã vạch với các tỷ lệ khung hình khác nhau, hãy giữ lại thể hiện `BarcodeGenerator` và chỉ thay đổi `DataBar.AspectRatio` trước mỗi lần `Save`. Điều này tránh việc khởi tạo lại generator cho mỗi ảnh, giảm tải đáng kể.

```csharp
var ratios = new[] { 10, 15, 20, 30 };
foreach (var ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    generator.Save($"DatabarAspectRatio{ratio}.png", BarCodeImageFormat.Png);
}
```

## Conclusion

Bây giờ bạn đã biết cách **tạo mã vạch Databar đa hướng** trong C# bằng Aspose.BarCode. Bằng cách khởi tạo `BarcodeGenerator`, đặt X‑dimension, điều chỉnh **set barcode aspect ratio**, và lưu dưới dạng PNG, bạn có thể tạo ra các ảnh mã vạch đáp ứng đa dạng yêu cầu nhãn.  

Tiếp theo, khám phá các chủ đề liên quan như **generate barcode image** cho QR code, **DataBar stacked omnidirectional barcode** validation, hoặc tích hợp các PNG đã tạo vào hoá đơn PDF bằng Aspose.PDF. Thử nghiệm các tỷ lệ khung hình và kích thước mô-đun khác nhau để tìm cấu hình tối ưu cho phần cứng in của bạn.

---


## Bạn nên học gì tiếp theo?


Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ code hoàn chỉnh với giải thích chi tiết từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách sử dụng barcode generator C# để tạo mã vạch DataBar đa hướng](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [databar stacked omnidirectional barcode trong C# – Hướng dẫn đầy đủ](/barcode/english/python-java/general/databar-stacked-omnidirectional-barcode-in-c-complete-guide/)
- [Cách tạo barcode trong C# – tạo ảnh barcode c# với DataBar Expanded](/barcode/english/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}