---
category: general
date: 2026-11-14
description: Hướng dẫn tạo mã vạch C# cho thấy cách tạo mã DataBar Omnidirectional,
  thiết lập kích thước X và điều chỉnh chiều cao thanh tính bằng pixel.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: vi
lastmod: 2026-11-14
og_description: Hướng dẫn tạo mã vạch C# giải thích chi tiết cách tạo mã vạch DataBar
  Omnidirectional, xác định XDimension bằng pixel và thay đổi chiều cao thanh cho
  đầu ra PNG.
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: Hướng dẫn tạo mã vạch C# – tạo mã DataBar.
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 'Hướng dẫn tạo mã vạch C#: DataBar Omnidirectional'
url: /vi/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hướng dẫn tạo barcode C# – tạo mã DataBar Omnidirectional

Nếu bạn đang tìm kiếm **hướng dẫn tạo barcode C#**, bạn đã đến đúng nơi. Hướng dẫn này sẽ chỉ cho bạn cách tạo mã DataBar Omnidirectional, cấu hình XDimension tính bằng pixel, và điều chỉnh chiều cao thanh để tạo ảnh PNG.

Bạn sẽ thấy một ví dụ hoàn chỉnh, có thể chạy được, bao gồm mọi thứ từ khởi tạo generator đến lưu nhiều ảnh với các chiều cao thanh khác nhau. Không cần tài liệu bên ngoài—chỉ cần sao chép mã, chạy nó, và bạn sẽ có hai tệp barcode sẵn sàng sử dụng.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 hoặc phiên bản mới hơn đã được cài đặt  
* Tham chiếu tới thư viện barcode cung cấp `BarcodeGenerator`, `EncodeTypes` và `BarCodeImageFormat` (ví dụ, Aspose.BarCode for .NET)  
* Kiến thức cơ bản về cú pháp C# và Visual Studio hoặc IDE ưa thích của bạn  

> **Mẹo chuyên nghiệp:** Nếu bạn đang sử dụng Aspose.BarCode, hãy thêm gói NuGet `Aspose.BarCode` vào dự án của bạn.

## Hướng dẫn tạo barcode C# – bước 1: tạo generator

Bước đầu tiên là khởi tạo một `BarcodeGenerator` với kiểu mã `DatabarOmniDirectional` và dữ liệu bạn muốn mã hoá.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Lý do quan trọng:* `EncodeTypes.DatabarOmniDirectional` báo cho thư viện tạo ra một barcode có thể đọc được từ bất kỳ hướng nào, rất phù hợp cho bao bì bán lẻ và logistics.

## Đặt XDimension tính bằng pixel cho barcode

X‑dimension xác định độ rộng của mô-đun nhỏ nhất (“pixel”) trong barcode. Đặt giá trị này bằng pixel giúp bạn kiểm soát chính xác mật độ hình ảnh của barcode.

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Giải thích:* Giá trị `2` pixel tạo ra một barcode đủ sắc nét cho hầu hết máy quét, đồng thời giữ kích thước tệp ảnh ở mức vừa phải.

## Điều chỉnh chiều cao thanh và lưu ảnh

Chiều cao thanh quyết định độ cao của các vạch. Bạn có thể tạo nhiều ảnh với các chiều cao khác nhau bằng cách thay đổi thuộc tính `BarHeight.Pixels` và gọi lại `Save`.

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

Giá trị enum `BarCodeImageFormat.Png` đảm bảo đầu ra là tệp PNG không mất dữ liệu, là định dạng được khuyến nghị cho đồ họa barcode vì nó giữ nguyên kích thước chính xác.

## Thay đổi chiều cao thanh để tạo nhiều ảnh

Bạn thường cần cùng một barcode ở các kích thước khác nhau—ví dụ, một cho nhãn nhỏ và một cho áp phích lớn. Thay đổi chiều cao thanh và tái sử dụng cùng một instance của generator:

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*Trường hợp đặc biệt:* Nếu chiều cao thanh được đặt quá thấp (ví dụ, dưới 10 px), một số máy quét có thể gặp khó khăn trong việc đọc mã. Luôn kiểm tra các ảnh đã tạo với phần cứng máy quét mục tiêu của bạn.

## Mã nguồn đầy đủ

Dưới đây là chương trình hoàn chỉnh mà bạn có thể sao chép‑dán vào một dự án console mới. Nó bao gồm tất cả các chỉ thị `using` cần thiết và minh họa cả hai biến thể chiều cao thanh.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

Chạy chương trình, thay thế `YOUR_DIRECTORY` bằng đường dẫn thư mục hợp lệ, và bạn sẽ thấy hai tệp PNG:

* `DatabarBarHeight30Pixels.png` – thanh cao 30 px  
* `DatabarBarHeight60Pixels.png` – thanh cao 60 px  

![hướng dẫn tạo barcode C# - kết quả](images/databar-example.png "Hướng dẫn tạo barcode C# hiển thị hai ảnh DataBar")

## Câu hỏi thường gặp

| Câu hỏi | Trả lời |
|----------|--------|
| **Tôi có thể thay đổi định dạng ảnh không?** | Có. Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, hoặc `Gif` tùy nhu cầu. PNG được ưu tiên vì chất lượng không mất dữ liệu. |
| **Nếu tôi cần một XDimension khác thì sao?** | Điều chỉnh `generator.Parameters.Barcode.XDimension.Pixels` thành bất kỳ số nguyên nào. Giá trị lớn hơn sẽ làm tăng tổng chiều rộng của barcode. |
| **DataBar Omnidirectional có phù hợp cho quét bằng điện thoại di động không?** | Có, miễn là kích thước in đáp ứng kích thước mô-đun tối thiểu của máy quét (thường là 0.33 mm). XDimension dựa trên pixel giúp bạn đạt được yêu cầu này. |
| **Làm sao chèn barcode vào PDF?** | Sau khi lưu PNG, sử dụng thư viện PDF (ví dụ, iTextSharp) để chèn ảnh vào trang PDF. |

## Kết luận

**Hướng dẫn tạo barcode C#** này đã chỉ cho bạn cách tạo mã DataBar Omnidirectional, đặt XDimension tính bằng pixel, và tạo các tệp PNG với các chiều cao thanh khác nhau. Giờ đây bạn có một đoạn mã có thể tái sử dụng và điều chỉnh cho bất kỳ dự án C# nào cần tạo barcode.

### Bước tiếp theo là gì?

* Khám phá các `EncodeTypes` khác như `Code128` hoặc `QR` để mở rộng danh mục barcode của bạn.  
* Kết hợp PNG đã tạo với thư viện tạo PDF để tạo hoá đơn có thể in.  
* Thử nghiệm `generator.Parameters.Barcode.Color` để thêm màu tùy chỉnh mà vẫn tuân thủ tiêu chuẩn máy quét.

Hãy tự do chỉnh sửa ví dụ, thử các chiều cao thanh khác, hoặc thay đổi định dạng đầu ra. Chúc bạn lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên đều bao gồm mã mẫu hoàn chỉnh với giải thích chi tiết từng bước, giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách đặt chiều rộng và điều chỉnh chiều cao cho barcode GS1 DataBar Omni‑Directional](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [Cách đặt chiều cao barcode, tạo barcode DataBar trong C#](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [Cách tạo barcode Databar omnidirectional trong C#](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}