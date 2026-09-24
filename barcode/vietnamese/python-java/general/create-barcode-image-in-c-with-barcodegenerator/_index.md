---
category: general
date: 2026-08-12
description: Tạo hình ảnh mã vạch trong C# bằng BarCodeGenerator. Tìm hiểu cách tạo
  DataBar, kiểm soát kích thước hình ảnh mã vạch và tạo nhiều mã vạch một cách hiệu
  quả.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: vi
lastmod: 2026-08-12
og_description: Tạo hình ảnh mã vạch trong C# với BarCodeGenerator. Hướng dẫn này
  trình bày chi tiết cách tạo mã DataBar, điều chỉnh kích thước hình ảnh mã vạch và
  tạo nhiều mã vạch.
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: Tạo hình ảnh mã vạch trong C# – hướng dẫn đầy đủ BarCodeGenerator
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: Tạo hình ảnh mã vạch trong C# với BarCodeGenerator
url: /vi/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình ảnh mã vạch trong C# với BarCodeGenerator

Nếu bạn cần **tạo hình ảnh mã vạch** trong một ứng dụng .NET, hướng dẫn này sẽ cho bạn thấy chính xác cách thực hiện với lớp `BarCodeGenerator`. Dù bạn đang xây dựng hệ thống POS bán lẻ hay công cụ theo dõi tồn kho, bạn sẽ học cách tạo các ký hiệu DataBar, kiểm soát kích thước hình ảnh mã vạch và tạo nhiều mã vạch trong một lần chạy.

Bạn cũng sẽ khám phá cách API **barcode generator c#** cho phép bạn điều chỉnh kích thước, chuyển đổi định dạng đầu ra và xử lý các trường hợp đặc biệt như chuỗi dữ liệu không hợp lệ. Khi kết thúc hướng dẫn, bạn có thể tự tin **tạo nhiều mã vạch** mà không cần viết mã lặp đi lặp lại.

## Yêu cầu trước

- .NET 6.0 hoặc phiên bản mới hơn đã được cài đặt  
- Môi trường phát triển (Visual Studio, Rider, hoặc VS Code)  
- Gói NuGet Aspose.BarCode cho .NET (hoặc bất kỳ thư viện tương thích nào cung cấp `BarCodeGenerator`)  

Bạn có thể thêm gói bằng:

```bash
dotnet add package Aspose.BarCode
```

## Nội dung hướng dẫn này

1. Cài đặt một thể hiện **barcode generator c#** cho mã hoá DataBar Omni‑directional.  
2. Điều chỉnh **kích thước hình ảnh mã vạch** bằng cách thay đổi X‑dimension và chiều cao thanh.  
3. Sử dụng vòng lặp để **tạo nhiều mã vạch** với các chiều cao khác nhau.  
4. Lưu các hình ảnh dưới dạng tệp PNG và xác minh kết quả.  

Tất cả các đoạn mã đều hoàn chỉnh và sẵn sàng để sao chép‑dán vào một dự án console mới.

![Ví dụ tạo hình ảnh mã vạch](barcode-example.png){alt="Ví dụ tạo hình ảnh mã vạch"}

## Bước 1: Khởi tạo trình tạo – các kiến thức cơ bản về tạo hình ảnh mã vạch

Bước đầu tiên là tạo một thể hiện của `BarCodeGenerator` với ký hiệu mong muốn. Đối với ký hiệu DataBar Omni‑directional, bạn sử dụng `EncodeTypes.DatabarOmniDirectional`.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**Tại sao điều này quan trọng:** Việc khởi tạo trình tạo xác định các quy tắc mã hoá và dữ liệu tải. Nếu bạn bỏ qua giá trị `EncodeTypes` đúng, thư viện sẽ tạo ra mã vạch không được hỗ trợ hoặc ném ra ngoại lệ.

## Bước 2: Cấu hình X‑dimension và chiều cao thanh – kiểm soát kích thước hình ảnh mã vạch

Kích thước hình ảnh của mã vạch được quyết định bởi hai tham số:

| Tham số | Điều nó điều khiển | Khoảng điển hình |
|-----------|------------------|---------------|
| `x_dimension.pixels` | Độ rộng của mô-đun nhỏ nhất (“điểm”) | 1 – 4 px |
| `bar_height.pixels`  | Chiều cao của các thanh dọc | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**Mẹo:** X‑dimension nhỏ hơn tạo ra hình ảnh độ phân giải cao hơn nhưng có thể khó quét trên máy in chất lượng thấp. Điều chỉnh giá trị dựa trên thiết bị quét mục tiêu của bạn.

## Bước 3: Lưu mã vạch đầu tiên – tạo hình ảnh mã vạch cho chiều cao 30 px

Bây giờ bạn có thể tạo hình ảnh và ghi nó vào đĩa. Phương thức `Save` nhận một đường dẫn tệp và một enum định dạng hình ảnh.

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**Kết quả mong đợi:** Một tệp PNG có tên `Databar30.png` xuất hiện trong `C:\Barcodes`. Mở tệp sẽ hiển thị ký hiệu DataBar Omni‑directional với mẫu rõ ràng, độ tương phản cao.

## Bước 4: Thay đổi chiều cao và tạo thêm hình ảnh – tạo nhiều mã vạch

Để **tạo nhiều mã vạch** với các kích thước khác nhau, bạn chỉ cần thay đổi thuộc tính `BarHeight` và gọi lại `Save`. Điều này tránh việc tạo lại trình tạo, giúp tiết kiệm bộ nhớ và thời gian CPU.

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**Tại sao cách này hoạt động:** Đối tượng `BarCodeGenerator` giữ toàn bộ trạng thái cấu hình. Thay đổi một thuộc tính duy nhất sẽ cập nhật engine render cho lần gọi `Save` tiếp theo, cho phép bạn **tạo nhiều mã vạch** một cách hiệu quả.

## Bước 5: Nâng cao – cách tạo DataBar với dữ liệu tùy chỉnh

Ví dụ trên sử dụng payload GS1 tĩnh. Trong các tình huống thực tế, bạn thường cần nhúng các định danh sản phẩm biến đổi. Thư viện chấp nhận bất kỳ chuỗi nào phù hợp với đặc tả DataBar.

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**Điểm chính:** Thiết lập `generator.CodeText` cập nhật dữ liệu đã mã hoá mà không cần tạo lại đối tượng. Đây là mẫu **cách tạo databar** được khuyến nghị khi xử lý các tập dữ liệu lớn.

## Bước 6: Xác minh và khắc phục – đảm bảo kích thước hình ảnh mã vạch đúng

Sau khi tạo các hình ảnh, bạn có thể muốn xác nhận một cách lập trình rằng kích thước khớp với mong đợi. Lớp `Image` từ `System.Drawing` có thể đọc tệp và báo cáo kích thước của nó.

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

Nếu chiều cao không phản ánh giá trị bạn đã đặt, hãy kiểm tra:

- **X‑dimension**: Giá trị quá nhỏ có thể khiến trình render làm tròn chiều cao.  
- **Định dạng hình ảnh**: Một số định dạng (ví dụ, JPEG) áp dụng nén có thể thay đổi kích thước pixel khi lưu. PNG giữ nguyên kích thước chính xác.

## Bước 7: Các thực hành tốt nhất cho kích thước hình ảnh mã vạch và hiệu năng

| Khuyến nghị | Lý do |
|----------------|--------|
| Giữ `x_dimension.pixels` trong khoảng 2 – 3 px cho hầu hết máy quét. | Cân bằng khả năng đọc và kích thước tệp. |
| Sử dụng PNG cho đầu ra không mất dữ liệu khi hình ảnh sẽ được in. | Đảm bảo kích thước chính xác và các cạnh sắc nét. |
| Tái sử dụng một thể hiện `BarCodeGenerator` duy nhất khi tạo nhiều mã vạch. | Giảm tải phân bổ đối tượng. |
| Xác thực chuỗi đầu vào theo tiêu chuẩn GS1 trước khi gán cho `CodeText`. | Ngăn ngừa ngoại lệ thời chạy và quét không hợp lệ. |
| Lưu các hình ảnh đã tạo trong thư mục riêng với quy ước đặt tên rõ ràng (ví dụ, `Databar_{GTIN}.png`). | Đơn giản hoá quá trình xử lý tiếp theo và theo dõi audit. |

## Ví dụ hoàn chỉnh hoạt động

Dưới đây là chương trình đầy đủ tích hợp tất cả các bước từ khởi tạo đến xác minh. Sao chép mã vào một dự án console mới và chạy nó.



## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoạt động đầy đủ với các giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo hình ảnh mã vạch – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [Tạo hình ảnh mã vạch DotCode – hàng & cột (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Cách tạo vùng yên tĩnh (Quiet Zone) cho ITF-14 bằng Aspose.BarCode cho .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}