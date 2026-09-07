---
category: general
date: 2026-09-07
description: Tạo mã vạch planet PNG trong C# nhanh chóng. Tìm hiểu cách tạo hình ảnh
  mã vạch planet bằng Aspose.BarCode với các thanh đầy và trống.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode png
- how to generate planet barcode
language: vi
lastmod: 2026-09-07
og_description: Tạo mã vạch Planet PNG trong C# nhanh chóng. Hãy theo hướng dẫn này
  để tìm hiểu cách tạo hình ảnh mã vạch Planet với các thanh đầy và trống bằng Aspose.BarCode.
og_image_alt: Planet barcode PNG image showing filled bars and empty‑bars version
og_title: Tạo mã vạch hành tinh PNG trong C# – hướng dẫn lập trình đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  headline: How to create planet barcode PNG with C# – step‑by‑step guide
  type: TechArticle
- description: Create planet barcode PNG in C# quickly. Learn how to generate planet
    barcode images using Aspose.BarCode with filled and empty bars.
  name: How to create planet barcode PNG with C# – step‑by‑step guide
  steps:
  - name: What if I need a different data format?
    text: 'Planet barcodes accept numeric strings up to 12 digits. If you pass a non‑numeric
      value, Aspose throws an `ArgumentException`. Validate the input before creating
      the generator:'
  - name: How do I change the image size without altering bar thickness?
    text: 'Use the `Resolution` property or scale the resulting bitmap after saving:'
  - name: Can I generate other image formats?
    text: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`, `Bmp`,
      or `Gif`. The API supports all common raster formats.
  - name: What about color customization?
    text: 'Set `BarColor` and `BackColor` on the `Barcode` parameters:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách tạo mã vạch hành tinh PNG bằng C# – hướng dẫn từng bước
url: /vi/python-java/general/how-to-create-planet-barcode-png-with-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch Planet PNG bằng C# – hướng dẫn từng bước

Nếu bạn cần **tạo tệp PNG mã vạch planet** trong C#, hướng dẫn này sẽ chỉ cho bạn các bước chính xác. Dù bạn đang xây dựng một tích hợp dịch vụ bưu chính hay một bảng điều khiển logistics, bạn sẽ học **cách tạo hình ảnh mã vạch planet** với cả thanh đầy và thanh rỗng bằng thư viện Aspose.BarCode.

Trong tutorial này bạn sẽ:

* Thiết lập thư mục đầu ra cho các ảnh của bạn.  
* Cấu hình một `BarcodeGenerator` cho ký hiệu Planet.  
* Tạo PNG với kiểu thanh đầy mặc định.  
* Tạo PNG với thanh rỗng để tạo độ tương phản trực quan.  

Không cần dịch vụ bên ngoài—mọi thứ chạy cục bộ trên .NET 6 hoặc phiên bản mới hơn.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn bạn có:

| Yêu cầu | Lý do quan trọng |
|-------------|----------------|
| .NET 6 SDK (hoặc mới hơn) | Cung cấp môi trường chạy cho ứng dụng console C#. |
| Visual Studio 2022 hoặc VS Code | Bất kỳ IDE nào có thể biên dịch dự án C#. |
| Aspose.BarCode for .NET (gói NuGet `Aspose.BarCode`) | Cung cấp lớp `BarcodeGenerator` dùng để vẽ mã vạch Planet. |
| Quyền ghi vào một thư mục trên đĩa | Các tệp PNG sẽ được lưu vào vị trí này. |

Cài đặt gói NuGet bằng lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

## Bước 1: Tạo dự án console mới

Mở terminal và chạy:

```bash
dotnet new console -n PlanetBarcodeDemo
cd PlanetBarcodeDemo
```

Lệnh này tạo một ứng dụng console C# tối thiểu có tên **PlanetBarcodeDemo**.

## Bước 2: Xác định thư mục đầu ra

Đoạn mã đầu tiên xác định nơi các tệp PNG được tạo sẽ được lưu. Có thể sử dụng đường dẫn tuyệt đối hoặc tương đối; chỉ cần đảm bảo thư mục tồn tại hoặc để chương trình tạo nó.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Define the output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");
        Directory.CreateDirectory(outputDir); // Guarantees the folder exists
```

*Why this step?* *Tại sao lại cần bước này?* Tách riêng đầu ra khỏi mã nguồn giúp dự án gọn gàng và tránh ghi đè nhầm.

## Bước 3: Tạo mã vạch Planet với các thanh đầy

Mã vạch Planet gồm các vòng tròn đồng tâm (được điền đầy mặc định). Chúng ta cấu hình kích thước X (độ rộng pixel của mỗi thanh) và sau đó lưu ảnh dưới dạng PNG.

```csharp
        // Step 3: Create a Planet barcode with the default (filled) bars
        BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetFilled.Parameters.Barcode.XDimension.Pixels = 4; // Controls bar thickness

        // Save the filled‑bars barcode as PNG
        string filledPath = Path.Combine(outputDir, "PostalPlanetFilledBars.png");
        planetFilled.Save(filledPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Filled‑bars barcode saved to: {filledPath}");
```

**Giải thích**

* `EncodeTypes.Planet` cho Aspose biết sử dụng ký hiệu Planet, thường được dùng trong dịch vụ bưu chính.  
* `XDimension.Pixels = 4` tạo kích thước rõ ràng, có thể in mà không cần tỷ lệ thủ công.  
* Phương thức `Save` ghi tệp PNG; bạn cũng có thể chọn JPEG hoặc BMP bằng cách thay đổi `BarCodeImageFormat`.

## Bước 4: Tạo mã vạch Planet với các thanh rỗng

Đôi khi cần hình ảnh có các thanh rỗng (trong suốt)—ví dụ khi mã vạch được đặt lên nền màu. Đặt `FilledBars` thành `false` sẽ tạo kiểu này.

```csharp
        // Step 4: Create a Planet barcode with empty bars
        BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
        planetEmpty.Parameters.Barcode.FilledBars = false; // Switch to empty‑bars mode

        // Save the empty‑bars barcode as PNG
        string emptyPath = Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
        planetEmpty.Save(emptyPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Empty‑bars barcode saved to: {emptyPath}");
```

**Giải thích**

* `FilledBars = false` tắt các vòng tròn đặc, chỉ để lại đường viền.  
* Tất cả các cài đặt khác (kích thước X, chuỗi dữ liệu) vẫn giống nhau, đảm bảo cả hai hình ảnh biểu diễn cùng một dữ liệu.

## Bước 5: Chạy chương trình và kiểm tra đầu ra

Biên dịch và thực thi:

```bash
dotnet run
```

Bạn sẽ thấy các thông báo trên console xác nhận các tệp đã được lưu, và thư mục `Barcodes` sẽ chứa:

* `PostalPlanetFilledBars.png` – một mã vạch Planet thanh đầy cổ điển.  
* `PostalPlanetEmptyBars.png` – cùng dữ liệu nhưng được vẽ với thanh rỗng.

Mở các tệp PNG bằng bất kỳ trình xem ảnh nào. Cả hai hình ảnh đều mã hoá chuỗi số **123456** và có thể được quét bằng các máy đọc mã vạch bưu chính tiêu chuẩn.

## Câu hỏi thường gặp và xử lý các trường hợp đặc biệt

### Nếu tôi cần định dạng dữ liệu khác thì sao?

Mã vạch Planet chấp nhận chuỗi số tối đa 12 chữ số. Nếu bạn truyền giá trị không phải số, Aspose sẽ ném `ArgumentException`. Hãy xác thực đầu vào trước khi tạo generator:

```csharp
if (!Regex.IsMatch(data, @"^\d{1,12}$"))
    throw new ArgumentException("Planet barcode data must be numeric and up to 12 digits.");
```

### Làm sao thay đổi kích thước ảnh mà không thay đổi độ dày thanh?

Sử dụng thuộc tính `Resolution` hoặc thay đổi kích thước bitmap sau khi lưu:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI for high‑resolution print
```

### Tôi có thể tạo các định dạng ảnh khác không?

Có. Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg`, `Bmp` hoặc `Gif`. API hỗ trợ tất cả các định dạng raster phổ biến.

### Còn tùy chỉnh màu thì sao?

Đặt `BarColor` và `BackColor` trên các tham số `Barcode`:

```csharp
planetFilled.Parameters.Barcode.BarColor = Color.DarkBlue;
planetFilled.Parameters.Barcode.BackColor = Color.LightYellow;
```

Các tùy chọn này hoạt động cho cả phiên bản thanh đầy và thanh rỗng.

## Mẹo chuyên nghiệp cho môi trường production

* **Cache generator** khi bạn cần tạo nhiều mã vạch với cùng cài đặt—khởi tạo đối tượng liên tục sẽ gây tốn tài nguyên.  
* **Dispose** các đối tượng `BarcodeGenerator` nếu bạn tạo nhiều trong vòng lặp (chúng thực thi `IDisposable`).  
* **Validate** thư mục đầu ra sớm để tránh ngoại lệ thời gian chạy trên các thư mục được bảo vệ ghi.  

## Kết luận

Bây giờ bạn đã biết cách **tạo tệp PNG mã vạch planet** trong C# và hiểu **cách tạo hình ảnh mã vạch planet** với cả kiểu thanh đầy và thanh rỗng. Ví dụ đầy đủ, có thể chạy này minh họa cách thiết lập thư mục đầu ra, cấu hình `BarcodeGenerator`, và lưu kết quả dưới dạng tệp PNG.

Tiếp theo, bạn có thể khám phá:

* Thêm **văn bản có thể đọc được** dưới mã vạch (`planetFilled.Parameters.Caption.Visible = true`).  
* Tích hợp các PNG đã tạo vào **hóa đơn PDF** bằng Aspose.PDF.  
* Chuyển sang các ký hiệu bưu chính khác như **IMB** hoặc **ITF** (`EncodeTypes.IMB`, `EncodeTypes.ITF`).  

Bạn có thể tự do thử nghiệm độ dày thanh, màu sắc và độ phân giải ảnh để phù hợp với yêu cầu cụ thể của ứng dụng. Chúc lập trình vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có ví dụ mã đầy đủ, kèm giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Create Planet Barcode in C# – Full Step‑by‑Step Guide](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Generate PNG Barcode with Aspose.BarCode for .NET: One-Dimensional Filled Bars](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-filled-bars-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}