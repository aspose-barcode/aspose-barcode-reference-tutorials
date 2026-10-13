---
category: general
date: 2026-09-29
description: Hướng dẫn tạo mã vạch C# cho thấy cách tạo mã vạch MicroPdf417, thay
  đổi kích thước, đặt số cột và tùy chỉnh kích thước mã vạch chỉ trong vài dòng.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: vi
lastmod: 2026-09-29
og_description: Hướng dẫn tạo mã vạch C# cho biết cách tạo mã vạch MicroPdf417, thay
  đổi kích thước, đặt số cột và tùy chỉnh kích thước mã vạch chỉ trong vài dòng.
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: Hướng dẫn tạo mã vạch C# – tạo và tùy chỉnh MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 'Hướng dẫn tạo trình tạo mã vạch C#: tạo MicroPdf417'
url: /vi/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hướng dẫn tạo Barcode generator C#: tạo MicroPdf417

Nếu bạn cần một **barcode generator C#** cho dự án .NET của mình, hướng dẫn này sẽ chỉ cho bạn cách tạo barcode MicroPdf417 từ đầu. Bạn sẽ học **cách tạo barcode**, thay đổi kích thước, đặt số cột, và **tùy chỉnh kích thước barcode** một cách dễ dàng.

MicroPdf417 là một ký hiệu 2‑D gọn nhẹ, phù hợp cho việc dán nhãn các bộ phận nhỏ, vé, hoặc thẻ kho. Khi kết thúc hướng dẫn này, bạn sẽ có một ứng dụng console đầy đủ, có thể chạy được, xuất ra hình PNG của barcode, và bạn sẽ hiểu cách mỗi tham số ảnh hưởng đến kích thước cuối cùng.

## Yêu cầu trước

* .NET 6.0 SDK hoặc phiên bản mới hơn (mã cũng hoạt động với .NET Framework 4.7+)
* Một IDE tương thích C# (Visual Studio, VS Code, Rider, v.v.)
* Gói NuGet **GroupDocs.Barcode** – cài đặt bằng  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

Không cần công cụ bên ngoài nào thêm; thư viện sẽ xử lý việc mã hoá, render và lưu file.

## Barcode generator C#: khởi tạo trình tạo

Bước đầu tiên là tạo một thể hiện của `BarcodeGenerator` và chỉ định ký hiệu (`EncodeTypes.MicroPdf417`) cùng với dữ liệu bạn muốn mã hoá.

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**Tại sao điều này quan trọng:**  
`BarcodeGenerator` là điểm vào cho mọi thao tác barcode. Constructor gắn **EncodeTypes** đã chọn (MicroPdf417) vào chuỗi dữ liệu thô. Thư viện tự động xử lý các ký tự Unicode như “Å” và “©”, vì vậy bạn không cần logic mã hoá bổ sung.

## Cách thay đổi kích thước của barcode

Độ đọc được của barcode phụ thuộc nhiều vào độ rộng mô-đun (X‑dimension). Đặt giá trị này thành số pixel lớn hơn làm cho các thanh rộng hơn và hình ảnh dễ quét hơn, đặc biệt trên màn hình độ phân giải thấp.

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Giải thích:**  
`XDimension.Pixels` kiểm soát độ rộng của một mô-đun barcode. Mặc định là 1 pixel, có thể trông mỏng trên màn hình DPI cao. Tăng lên 2 pixel sẽ gấp đôi độ rộng tổng thể mà không ảnh hưởng đến dữ liệu đã mã hoá.

**Mẹo:** Nếu bạn dự định in barcode ở 300 dpi, giá trị 3 hoặc 4 pixel thường cho cân bằng tốt nhất giữa kích thước và độ tin cậy khi quét.

## Cách đặt số cột để kiểm soát kích thước

MicroPdf417 cho phép bạn chỉ định số cột (tối đa 4). Ít cột hơn tạo ra barcode cao hơn; nhiều cột hơn làm barcode rộng hơn nhưng ngắn hơn. Điều chỉnh giá trị này là cách chính để **tùy chỉnh kích thước barcode**.

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**Tại sao cách này hoạt động:**  
Thuộc tính `Pdf417.Columns` được chia sẻ cho tất cả các ký hiệu dựa trên PDF417, bao gồm MicroPdf417. Đặt nó ở mức tối đa (4) sẽ phân bố dữ liệu trên bố cục rộng nhất có thể, giảm chiều cao tổng thể. Nếu bạn cần chiều cao gọn hơn, giảm số cột xuống 2 hoặc 3.

**Trường hợp đặc biệt:** Khi chuỗi dữ liệu dài, thư viện có thể tự động tăng số hàng để chứa nội dung, bất kể số cột. Giữ payload dưới 50 ký tự để kích thước dự đoán được.

## Tùy chỉnh kích thước barcode cho các đầu ra khác nhau

Ngoài X‑dimension và số cột, bạn có thể ảnh hưởng đến kích thước hình ảnh cuối cùng bằng cách chọn định dạng ảnh và DPI phù hợp. PNG là không mất dữ liệu, hoàn hảo cho hiển thị web, trong khi BMP hoặc TIFF có thể thích hợp hơn cho in chất lượng cao.

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

Nếu bạn cần DPI cao hơn, bạn có thể đặt nó một cách rõ ràng:

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**Kết quả:** File PNG đã lưu chứa một barcode MicroPdf417 sắc nét, tuân theo các kích thước bạn cấu hình. Mở file trong bất kỳ trình xem ảnh nào để xác nhận kích thước hiển thị.

### Kết quả mong đợi

Chạy chương trình sẽ tạo ra một file có tên **MicroPdf417.png** (hoặc **MicroPdf417_300dpi.png** nếu bạn đặt DPI). Barcode sẽ trông giống như hình minh họa dưới đây:

![Kết quả Barcode generator C# hiển thị một MicroPdf417 PNG](barcode-micro-pdf417.png)

*Văn bản thay thế:* *Kết quả Barcode generator C# hiển thị một MicroPdf417 PNG*

Quét hình ảnh bằng một đầu đọc barcode 2‑D tiêu chuẩn sẽ trả về chuỗi gốc `Åspóse.Barcóde©`.

## Mã nguồn đầy đủ để sao chép nhanh

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

Sao chép mã vào một dự án console mới, khôi phục các gói NuGet, và chạy `dotnet run`. Console sẽ xác nhận vị trí ảnh, và bạn sẽ thấy barcode đã tạo trong thư mục dự án của mình.

## Các câu hỏi thường gặp và khắc phục sự cố

| Question | Answer |
|----------|--------|
| **Nếu barcode bị mờ?** | Tăng `XDimension.Pixels` hoặc DPI (`Parameters.Image.DpiX/Y`). Cả hai đều làm lớn hơn các mô-đun và cải thiện độ trung thực hình ảnh. |
| **Tôi có thể dùng định dạng ảnh khác không?** | Có. Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, hoặc `Tiff`. PNG vẫn là lựa chọn an toàn nhất cho chất lượng không mất dữ liệu. |
| **Dữ liệu của tôi chứa emoji—có được mã hoá không?** | MicroPdf417 hỗ trợ UTF‑8, vì vậy hầu hết các emoji sẽ được mã hoá đúng. Nếu gặp lỗi, hãy kiểm tra chuỗi đã được chuẩn hoá đúng (`System.Text.Encoding.UTF8`). |
| **Làm sao để tạo các ký hiệu khác?** | Thay `EncodeTypes.MicroPdf417` bằng bất kỳ giá trị nào khác từ `EncodeTypes` ( |

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ, có giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo hình ảnh Barcode trong C# – Hướng dẫn MicroPdf417](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [Cách tạo barcode PDF417 trong C# với kích thước tùy chỉnh](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}