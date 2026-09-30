---
category: general
date: 2026-09-10
description: Cách thiết lập mã vạch trong C# bằng Trình tạo mã vạch. Điều chỉnh độ
  rộng mô-đun mã vạch, tạo hình ảnh mã vạch và học cách lưu các tệp mã vạch.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- c# barcode generator
- barcode module width
- how to generate barcode
- how to save barcode
language: vi
lastmod: 2026-09-10
og_description: Cách thiết lập mã vạch trong C# với Trình tạo mã vạch. Tìm hiểu cách
  điều chỉnh độ rộng mô-đun, tạo mã vạch và lưu ảnh mã vạch một cách hiệu quả.
og_image_alt: Screenshot showing a Planet barcode with filled and empty bars generated
  by C# code
og_title: Cách thiết lập các thuộc tính mã vạch bằng C# Barcode Generator
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode in C# using a Barcode Generator. Adjust barcode
    module width, generate barcode images, and learn how to save barcode files.
  headline: How to set barcode properties with the C# Barcode Generator
  type: TechArticle
tags:
- barcode
- c#
- image generation
title: Cách thiết lập các thuộc tính mã vạch bằng Trình tạo Mã vạch C#
url: /vi/python-java/general/how-to-set-barcode-properties-with-the-c-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thiết lập thuộc tính mã vạch với Trình tạo Mã vạch C#

Việc thiết lập thuộc tính mã vạch là rất quan trọng khi bạn cần kiểm soát chính xác kiểu dáng hình ảnh của mã vạch. Hướng dẫn này sẽ chỉ cho bạn cách tạo mã vạch Planet, điều chỉnh độ rộng mô-đun của mã vạch và lưu ảnh mã vạch bằng Trình tạo Mã vạch C#.

Bạn sẽ thấy một ví dụ hoàn chỉnh, có thể chạy được, bao gồm mọi bước từ tạo đối tượng mã vạch đến ghi các tệp PNG ra đĩa. Không cần tài liệu bên ngoài—chỉ cần đoạn mã dưới đây và thư viện Aspose.BarCode (hoặc bất kỳ SDK mã vạch tương thích nào). Khi kết thúc tutorial, bạn sẽ có thể trả lời các câu hỏi như “cách tạo mã vạch với kích thước tùy chỉnh?” và “cách lưu mã vạch ở các định dạng khác nhau?”.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

* .NET 6.0 hoặc phiên bản mới hơn được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE C# nào)  
* Gói **Aspose.BarCode** trên NuGet (hoặc thư viện khác cung cấp `BarcodeGenerator`)  

Bạn có thể thêm gói bằng lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

## Cách thiết lập độ rộng mô-đun của mã vạch

*Độ rộng mô-đun* (còn gọi là X‑dimension) xác định kích thước pixel của mỗi thanh mảnh trong mã vạch. Việc thiết lập giá trị này cho phép bạn kiểm soát kích thước tổng thể và khả năng đọc của hình ảnh.

```csharp
// Create a barcode generator for the Planet symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Tại sao điều này quan trọng*: X‑dimension lớn hơn tạo ra mã vạch to hơn, dễ đọc hơn cho máy quét ở khoảng cách xa, trong khi giá trị nhỏ hơn giảm kích thước tệp cho việc hiển thị trên màn hình.

## Tạo mã vạch với các thanh được tô đầy

Kiểu mặc định cho mã vạch Planet sử dụng **filled bars** (các thanh đen đặc). Đoạn mã sau tạo hình ảnh và lưu dưới dạng PNG.

```csharp
// Save the barcode with filled bars
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

> **Kết quả**: `PostalPlanetFilledBars.png` chứa một mã vạch Planet tiêu chuẩn, trong đó mọi thanh đều được tô đầy.

## Tạo mã vạch với thanh rỗng

Đôi khi bạn cần một mã vạch chỉ hiển thị đường viền của các thanh (empty bars). Để đạt được điều này, bạn sao chép trình tạo, giữ nguyên độ rộng mô-đun và tắt cờ `FilledBars`.

```csharp
// Duplicate the generator for an empty‑bar version
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Apply the same X‑dimension
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars so only the outlines are drawn
emptyBarGenerator.Parameters.Barcode.FilledBars = false;

// Save the empty‑bar barcode
emptyBarGenerator.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

> **Kết quả**: `PostalPlanetEmptyBars.png` hiển thị cùng dữ liệu nhưng các thanh không được tô, hữu ích cho các tài liệu thiết kế nặng nơi bạn muốn mã vạch hòa nhập với nền.

## Cách lưu mã vạch ở các định dạng khác nhau

Phương thức `Save` chấp nhận bất kỳ định dạng nào được SDK hỗ trợ, chẳng hạn như **Jpeg**, **Bmp**, **Gif**, hoặc **Svg**. Thay đổi định dạng chỉ cần hoán đổi giá trị enum `BarCodeImageFormat`.

```csharp
// Example: save as SVG for lossless scaling
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanet.svg", BarCodeImageFormat.Svg);
```

*Mẹo*: Sử dụng SVG khi bạn cần đồ họa vector có thể phóng to mà không bị pixel hoá, đặc biệt cho các PDF sẵn sàng in.

## Ví dụ đầy đủ, có thể chạy

Kết hợp tất cả các phần lại sẽ cho bạn một chương trình tự chứa, có thể dán vào một ứng dụng console.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create a filled‑bar Planet barcode
        BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4; // barcode module width
        filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // 2. Create an empty‑bar version of the same barcode
        BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4; // same module width
        emptyGenerator.Parameters.Barcode.FilledBars = false;   // how to set barcode to empty bars
        emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

        // 3. Optional: save as SVG for scalable use
        filledGenerator.Save("PostalPlanet.svg", BarCodeImageFormat.Svg);
    }
}
```

**Kết quả mong đợi**

| Tên tệp                        | Mô tả                                     |
|--------------------------------|-------------------------------------------|
| `PostalPlanetFilledBars.png`   | Mã vạch Planet với các thanh đen đặc      |
| `PostalPlanetEmptyBars.png`    | Cùng dữ liệu, các thanh được vẽ dưới dạng đường viền |
| `PostalPlanet.svg`             | Phiên bản vector có thể phóng to mà không mất chất lượng |

Chạy chương trình, mở các tệp đã tạo và xác nhận rằng các mã vạch khớp với chuỗi số “123456”.

## Các biến thể phổ biến và trường hợp đặc biệt

| Tình huống                                 | Điều chỉnh                                                            |
|--------------------------------------------|-----------------------------------------------------------------------|
| Cần mã vạch dày hơn                        | Tăng `XDimension.Pixels` (ví dụ: `8`)                                 |
| Muốn giảm kích thước tệp                   | Sử dụng `BarCodeImageFormat.Jpeg` hoặc giảm X‑dimension               |
| Tạo các loại mã vạch khác                 | Thay `EncodeTypes.Planet` bằng `EncodeTypes.Code128`, `QR`, v.v.      |
| In trên máy in độ phân giải cao            | Lưu dưới dạng `BarCodeImageFormat.Tiff` để có đầu ra raster không mất dữ liệu |
| Chạy trên máy chủ không có giao diện người dùng | Không cần mã UI; trình tạo hoạt động trong ngữ cảnh console hoặc service |

**Mẹo chuyên nghiệp**: Luôn kiểm tra mã vạch đã tạo bằng máy quét hoặc công cụ xác minh trước khi đưa vào sản xuất. Độ rộng mô-đun hoặc định dạng không đúng có thể gây lỗi quét.

## Kết luận

Bạn đã biết cách thiết lập thuộc tính mã vạch bằng Trình tạo Mã vạch C#, cách điều chỉnh độ rộng mô-đun, cách tạo cả kiểu thanh đầy và thanh rỗng, và cách lưu mã vạch ở định dạng PNG hoặc SVG. Những bước này cung cấp nền tảng vững chắc để thêm chức năng tạo mã vạch vào bất kỳ ứng dụng .NET nào.

Tiếp theo, hãy khám phá các chủ đề liên quan như **c# barcode generator performance tuning**, **embedding barcodes in PDF documents**, và **creating QR codes with custom colors**. Thử nghiệm với các `EncodeTypes` và định dạng ảnh khác nhau để tìm ra giải pháp phù hợp nhất cho dự án của bạn.

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích chi tiết từng bước, giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Barcode Generator Tutorial: How to Generate PDF417 Barcode in C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}