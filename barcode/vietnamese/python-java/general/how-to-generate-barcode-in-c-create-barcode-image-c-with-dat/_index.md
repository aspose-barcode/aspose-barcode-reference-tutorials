---
category: general
date: 2026-08-22
description: Cách tạo mã vạch trong C# bằng Aspose.BarCode. Học cách tạo hình ảnh
  mã vạch C# từng bước, tắt thành phần 2‑D và lưu dưới dạng tệp PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: vi
lastmod: 2026-08-22
og_description: Cách tạo mã vạch trong C# với Aspose.BarCode. Hướng dẫn này cho bạn
  biết cách tạo hình ảnh mã vạch bằng C# sử dụng DataBar Expanded, bật/tắt thành phần
  2‑D và lưu dưới dạng tệp PNG.
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: Cách tạo mã vạch trong C# – hướng dẫn đầy đủ để tạo hình ảnh mã vạch bằng
  C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: Cách tạo mã vạch trong C# – tạo hình ảnh mã vạch C# với DataBar Expanded
url: /vi/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch trong C# – tạo hình ảnh mã vạch c# với DataBar Expanded

Tạo mã vạch trong C# là một yêu cầu thường gặp khi bạn cần nhúng dữ liệu có thể đọc được bằng máy vào ứng dụng của mình. Hướng dẫn này chỉ cho bạn cách tạo hình ảnh mã vạch c# bằng thư viện Aspose.BarCode, tắt thành phần tổng hợp 2‑D và lưu kết quả dưới dạng file PNG.

Bạn sẽ thấy một chương trình hoàn chỉnh, có thể chạy được, giải thích mọi tùy chọn cấu hình, và các mẹo để tùy chỉnh đầu ra. Không cần tài liệu bên ngoài—chỉ cần đoạn mã dưới đây và môi trường phát triển .NET.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

* .NET 6.0 SDK hoặc phiên bản mới hơn được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ .NET)  
* Gói NuGet Aspose.BarCode for .NET (`Aspose.BarCode`)  

Bạn có thể thêm gói bằng lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

Thư viện cung cấp lớp `BarcodeGenerator` được sử dụng xuyên suốt trong tutorial này.

## Bước 1: Thiết lập dự án và nhập không gian tên

Tạo một ứng dụng console mới và nhập các không gian tên cần thiết:

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

Không gian tên `Aspose.BarCode.Generation` chứa tất cả các lớp cần để cấu hình và tạo mã vạch.

## Bước 2: Khởi tạo trình tạo mã vạch DataBar Expanded

Dòng lệnh chức năng đầu tiên tạo một `BarcodeGenerator` cho ký hiệu **DataBar Expanded** và cung cấp chuỗi dữ liệu thô. Chuỗi dữ liệu tuân theo định dạng GS1 Application Identifier `(01)12345678901231`.

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

Việc tạo trình tạo sẽ cấp phát canvas bitmap nội bộ, vì vậy bạn có thể điều chỉnh kích thước và giao diện trước khi render.

## Bước 3: Định nghĩa độ rộng mô-đun (X‑dimension)

X‑dimension kiểm soát độ rộng của phần tử mã vạch nhỏ nhất. Đặt giá trị bằng pixel cho phép bạn kiểm soát chính xác kích thước ảnh cuối cùng.

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Giá trị `2` pixel thường phù hợp cho hiển thị trên màn hình; tăng lên nếu cần in với độ phân giải cao hơn.

## Bước 4: Tắt thành phần tổng hợp 2‑D

DataBar Expanded có thể bao gồm một thành phần 2‑D mang thông tin bổ sung. Để tạo mã vạch **không** có thành phần này, đặt cờ thành `false`.

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

Việc tắt thành phần sẽ giảm độ phức tạp hình ảnh và tạo ra file PNG nhỏ hơn.

## Bước 5: Lưu hình ảnh mã vạch mà không có thành phần 2‑D

Chọn thư mục đầu ra và ghi ảnh ra đĩa. Enum `BarCodeImageFormat.Png` đảm bảo file PNG không mất dữ liệu.

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

Sau lệnh này, `Databar2DComponentDisabled.png` sẽ chứa một mã DataBar Expanded sạch sẽ.

## Bước 6: Bật lại thành phần tổng hợp 2‑D

Nếu bạn cần lớp dữ liệu bổ sung, bật lại cờ. Cùng một thể hiện của trình tạo có thể được tái sử dụng, tránh việc tạo đối tượng thứ hai.

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Bước 7: Lưu hình ảnh mã vạch với thành phần 2‑D được bật

Render ảnh thứ hai bằng cùng các thiết lập, ngoại trừ cờ 2‑D.

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

Bây giờ `Databar2DComponentEnabled.png` sẽ hiển thị mã vạch có mẫu 2‑D bổ sung.

## Mã nguồn đầy đủ

Sao chép toàn bộ đoạn mã dưới đây vào `Program.cs` và chạy dự án. Chương trình sẽ tạo cả hai file PNG trong thư mục bạn chỉ định.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### Kết quả mong đợi

Chạy chương trình sẽ in ra:

```
Barcode images generated successfully.
```

và tạo hai file:

* `Databar2DComponentDisabled.png` – mã vạch không có thành phần 2‑D  
* `Databar2DComponentEnabled.png` – mã vạch có thành phần 2‑D  

Mở các file PNG bằng bất kỳ trình xem ảnh nào để kiểm tra sự khác biệt về hình ảnh.

## Các biến thể phổ biến và trường hợp đặc biệt

| Tình huống | Điều chỉnh |
|-----------|------------|
| **Ký hiệu khác** | Thay `EncodeTypes.DatabarExpanded` bằng giá trị khác, ví dụ `EncodeTypes.Code128`. |
| **Độ phân giải cao hơn** | Tăng `XDimension.Pixels` lên 4 hoặc 5, hoặc đặt `Resolution` trong `barcodeGenerator.Parameters.Image`. |
| **Định dạng ảnh khác** | Sử dụng `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, hoặc `BarCodeImageFormat.Svg`. |
| **Chạy trong ứng dụng web** | Stream byte ảnh trực tiếp tới phản hồi HTTP thay vì lưu vào đĩa. |
| **Quản lý bộ nhớ** | Bao bọc trình tạo trong khối `using` nếu bạn nhắm tới .NET Framework để đảm bảo tài nguyên không quản lý được giải phóng. |

## Mẹo chuyên nghiệp

* **Tái sử dụng trình tạo** – Chỉ thay đổi cờ 2‑D mà không tạo lại đối tượng giúp tiết kiệm chu kỳ CPU.  
* **Xác thực dữ liệu** – Dữ liệu GS1 phải tuân thủ độ dài và quy tắc checksum chính xác; đầu vào không hợp lệ sẽ ném `ArgumentException`.  
* **Xử lý hàng loạt** – Lặp qua một tập hợp các chuỗi dữ liệu, bật/tắt cờ 2‑D khi cần, và lưu mỗi ảnh với tên file duy nhất.  

## Kết luận

Bây giờ bạn đã biết cách tạo mã vạch trong C# và tạo hình ảnh mã vạch c# với kiểm soát đầy đủ thành phần tổng hợp 2‑D. Ví dụ minh họa cách khởi tạo trình tạo, cấu hình X‑dimension, bật/tắt thành phần, và lưu file PNG. Từ đây bạn có thể khám phá các ký hiệu khác, nhúng ảnh vào PDF, hoặc tích hợp việc tạo mã vạch vào dịch vụ ASP.NET Core.

--- 

*Bước tiếp theo*: thử tạo mã QR, thử nghiệm các độ phân giải ảnh khác nhau, hoặc nhúng các PNG đã tạo vào PDF bằng Aspose.PDF. Những mở rộng này dựa trên cùng một API `BarcodeGenerator` và giúp duy trì quy trình làm việc nhất quán.

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm mã mẫu đầy đủ với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}