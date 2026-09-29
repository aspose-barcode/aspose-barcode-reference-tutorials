---
category: general
date: 2026-09-29
description: Tạo mã vạch GS1 trong C# và tạo hình ảnh PNG cho mã vạch bằng BarcodeGenerator.
  Thực hiện theo hướng dẫn từng bước để xuất hình ảnh mã vạch một cách hiệu quả.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode gs1
- generate barcode png
- barcode generator c#
- how to generate barcode
- export barcode image
language: vi
lastmod: 2026-09-29
og_description: Tạo mã vạch GS1 trong C# và tạo các tệp PNG mã vạch bằng BarcodeGenerator.
  Theo dõi hướng dẫn đầy đủ này để xuất nhanh hình ảnh mã vạch.
og_image_alt: Generated GS1 MicroPDF417 barcode saved as a PNG file
og_title: Tạo mã vạch GS1 trong C# – xuất ra PNG trong vài phút
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create barcode GS1 in C# and generate barcode PNG images using BarcodeGenerator.
    Follow a step‑by‑step guide to export barcode image efficiently.
  headline: Create barcode GS1 in C# and export it as PNG
  type: TechArticle
tags:
- barcode
- C#
- GS1
- PNG
- Aspose
title: Tạo mã vạch GS1 trong C# và xuất ra PNG
url: /vi/net/gs1-barcode-encoding/create-barcode-gs1-in-c-and-export-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch GS1 trong C# và xuất ra PNG

Nếu bạn cần **tạo mã vạch GS1** trong một ứng dụng .NET, hướng dẫn này sẽ cho bạn thấy cách thực hiện chính xác. Bạn sẽ thấy một giải pháp ngắn gọn tạo ra một hình ảnh PNG của mã vạch và xuất hình ảnh mã vạch ra đĩa, tất cả đều sử dụng lớp Aspose.BarCode `BarcodeGenerator`.

Việc tạo mã vạch GS1 là một yêu cầu phổ biến cho hệ thống quản lý tồn kho, vận chuyển và điểm bán hàng. Khi kết thúc hướng dẫn này, bạn sẽ có thể viết một chương trình C# nhỏ tạo ra mã vạch MicroPDF417 tuân thủ GS1 và lưu nó dưới dạng tệp PNG chất lượng cao.

## Yêu cầu trước

* **.NET 6** (hoặc bất kỳ phiên bản .NET nào sau này) đã được cài đặt.
* **Visual Studio 2022** hoặc bất kỳ IDE nào hỗ trợ C#.
* Gói NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`) – nó cung cấp API `BarcodeGenerator` được sử dụng trong các ví dụ.
* Kiến thức cơ bản về cú pháp C#.

> **Mẹo:** Sử dụng phiên bản cộng đồng miễn phí của Aspose.BarCode khi thử nghiệm; phiên bản đầy đủ sẽ loại bỏ mọi watermark đánh giá.

## Bước 1 – Tạo mã vạch GS1 với BarcodeGenerator

Điều đầu tiên bạn cần làm là khởi tạo `BarcodeGenerator` cho định dạng *MicroPDF417* và cung cấp cho nó một chuỗi dữ liệu GS1. Các Application Identifier (AI) của GS1 được bao trong dấu ngoặc đơn, ví dụ `(01)` cho GTIN‑14 và `(21)` cho số sê-ri.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// GS1 data: (01) – GTIN‑14, (21) – serial number
string gs1Data = "(01)12345678901234(21)ABC123";

// Initialise the generator for MicroPDF417 (GS1 compatible)
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);
```

**Tại sao điều này quan trọng:**  
`EncodeTypes.MicroPdf417` tự động xử lý đầu vào như dữ liệu GS1 khi chuỗi chứa các AI hợp lệ. Điều này đảm bảo mã vạch được tạo tuân thủ tiêu chuẩn GS1 mà không cần cấu hình thêm.

## Bước 2 – Đặt kích thước mã vạch để đạt kích thước tối ưu

Kích thước hiển thị của mã vạch được kiểm soát bởi **X‑dimension** (chiều rộng của một mô-đun). Điều chỉnh `XDimension.Pixels` cho phép bạn tinh chỉnh kích thước hình ảnh cuối cùng trong khi vẫn duy trì khả năng đọc.

```csharp
// Set the module width to 2 pixels – a good balance for screen and print
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Cách tạo PNG mã vạch** – X‑dimension không ảnh hưởng đến dữ liệu được mã hoá; nó chỉ thay đổi kích thước vật lý của hình ảnh được tạo. Nếu bạn cần một mã vạch lớn hơn cho việc in độ phân giải cao, hãy tăng giá trị này (ví dụ, `3` hoặc `4`).

## Bước 3 – Tạo PNG mã vạch và xuất hình ảnh mã vạch

Bây giờ bạn có thể render mã vạch và ghi nó vào tệp PNG. Phương thức `Save` nhận đường dẫn đích và định dạng hình ảnh mong muốn.

```csharp
// Define the output folder (ensure it exists)
string outputFolder = Path.Combine(Environment.CurrentDirectory, "output");
Directory.CreateDirectory(outputFolder);

// Export the barcode image as PNG
string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
generator.Save(pngPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode image saved to: {pngPath}");
```

**Điều gì xảy ra bên trong:**  
`BarcodeGenerator.Save` raster hoá mã vạch thành bitmap, áp dụng X‑dimension bạn đã thiết lập trước đó, và mã hoá bitmap thành tệp PNG. Tệp kết quả có thể được sử dụng trực tiếp trong các trang web, in lên nhãn, hoặc nhúng vào PDF.

## Ví dụ mã nguồn đầy đủ

Dưới đây là một ứng dụng console hoàn chỉnh, tự chứa, bạn có thể sao chép, dán và chạy. Nó minh họa **cách tạo tệp PNG mã vạch**, **xuất hình ảnh mã vạch**, và bao gồm xử lý lỗi cơ bản.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Gs1BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            try
            {
                // 1️⃣ Initialise the barcode generator for GS1 MicroPDF417
                string gs1Data = "(01)12345678901234(21)ABC123";
                BarcodeGenerator generator = new BarcodeGenerator(
                    EncodeTypes.MicroPdf417, gs1Data);

                // 2️⃣ Adjust X‑dimension to control the visual size
                generator.Parameters.Barcode.XDimension.Pixels = 2;

                // 3️⃣ Prepare output folder
                string outputFolder = Path.Combine(
                    Environment.CurrentDirectory, "output");
                Directory.CreateDirectory(outputFolder);

                // 4️⃣ Save the barcode as PNG (export barcode image)
                string pngPath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
                generator.Save(pngPath, BarCodeImageFormat.Png);

                Console.WriteLine($"✅ Barcode created and saved as PNG:");
                Console.WriteLine(pngPath);
            }
            catch (Exception ex)
            {
                Console.Error.WriteLine($"Error: {ex.Message}");
            }
        }
    }
}
```

### Kết quả mong đợi

Khi bạn chạy chương trình, bạn sẽ thấy:

```
✅ Barcode created and saved as PNG:
C:\Path\To\Your\App\output\GS1MicroPdf417.png
```

Mở tệp PNG sẽ hiển thị một mã vạch **GS1 MicroPDF417** rõ ràng, mã hoá GTIN‑14 `12345678901234` và số sê-ri `ABC123`. Quét nó bằng bất kỳ máy quét tương thích GS1 nào sẽ trả về chuỗi dữ liệu gốc.

## Những lỗi thường gặp và thực hành tốt nhất

| Vấn đề | Nguyên nhân | Cách tránh |
|-------|-------------|------------|
| **Định dạng AI không đúng** | Thiếu dấu ngoặc hoặc thứ tự sai khiến mã vạch không phải GS1. | Luôn bao mỗi AI trong dấu ngoặc, ví dụ `(01)`. |
| **X‑dimension quá nhỏ** | Mã vạch trở nên không đọc được trên thiết bị độ phân giải thấp. | Giữ `XDimension.Pixels` ≥ 2 cho hầu hết máy in; tăng lên cho đầu ra DPI cao. |
| **Thư mục đầu ra không tồn tại** | `Save` ném `DirectoryNotFoundException`. | Sử dụng `Directory.CreateDirectory` trước khi gọi `Save`. |
| **Sử dụng EncodeType sai** | Một số loại (ví dụ, `Code128`) không hỗ trợ dữ liệu GS1 mặc định. | Chọn `EncodeTypes.MicroPdf417` hoặc bất kỳ loại nào tương thích GS1. |
| **Thiếu tham chiếu NuGet** | Lỗi biên dịch như `The type or namespace name 'Aspose' could not be found`. | Cài đặt gói `Aspose.BarCode` qua NuGet. |

## Mở rộng ví dụ

* **Định dạng hình ảnh khác** – Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Gif`, hoặc `Bmp` nếu bạn cần định dạng khác.
* **Đầu ra độ phân giải cao hơn** – Đặt `generator.Parameters.ImageResolution.DpiX` và `DpiY` trước khi lưu.
* **Nhúng vào PDF** – Sử dụng `Aspose.Pdf` để chèn PNG vào hóa đơn PDF hoặc nhãn.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch GS1** trong C# bằng Aspose.BarCode `BarcodeGenerator`, **tạo PNG mã vạch**, và **xuất hình ảnh mã vạch** ra hệ thống tệp. Hướng dẫn đã bao phủ mọi bước — từ khởi tạo generator với dữ liệu GS1, điều chỉnh X‑dimension, đến lưu tệp PNG cuối cùng — đồng thời giải quyết các lỗi thường gặp và đưa ra các ý tưởng mở rộng.

Bạn có thể thoải mái thử nghiệm với các Application Identifier GS1 khác, các loại mã vạch khác nhau, hoặc hình ảnh độ phân giải cao hơn. Khi bạn nắm vững những kiến thức cơ bản này, việc tạo mã vạch tuân thủ cho quản lý tồn kho, vận chuyển hoặc bán lẻ sẽ trở thành một phần thường ngày trong bộ công cụ .NET của bạn.

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ hoạt động với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo Hình Ảnh Mã Vạch GS1 trong C# – Cách Tạo Mã Vạch C# Nhanh](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [Tạo PNG Mã Vạch trong C# – Hướng Dẫn Từng Bước](/barcode/english/python-java/general/create-barcode-png-in-c-step-by-step-guide/)
- [Tạo Hình Ảnh Mã Vạch trong C# – Hướng Dẫn Lập Trình Toàn Diện](/barcode/english/python-java/general/create-barcode-image-in-c-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}