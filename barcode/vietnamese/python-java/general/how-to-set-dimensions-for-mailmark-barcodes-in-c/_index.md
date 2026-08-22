---
category: general
date: 2026-08-22
description: Tìm hiểu cách đặt kích thước cho mã vạch Mailmark trong C# và lưu chúng
  dưới dạng ảnh PNG. Bao gồm mã nguồn đầy đủ, giải thích và mẹo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set dimensions
- Mailmark barcode C# example
- BarcodeGenerator dimensions
- set barcode size in C#
- save barcode as PNG
language: vi
lastmod: 2026-08-22
og_description: Cách đặt kích thước cho mã vạch Mailmark trong C# và xuất chúng dưới
  dạng tệp PNG. Theo dõi ví dụ đầy đủ và tránh các lỗi thường gặp.
og_image_alt: Screenshot of two generated Mailmark barcode PNG files showing different
  dimensions
og_title: Cách đặt kích thước cho mã vạch Mailmark trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to set dimensions for Mailmark barcodes in C# and save them
    as PNG images. Includes full code, explanations, and tips.
  headline: How to set dimensions for Mailmark barcodes in C#
  type: TechArticle
tags:
- C#
- barcode
- Mailmark
- image generation
title: Cách đặt kích thước cho mã vạch Mailmark trong C#
url: /vi/python-java/general/how-to-set-dimensions-for-mailmark-barcodes-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đặt kích thước cho mã vạch Mailmark trong C#

Nếu bạn cần **cách đặt kích thước** cho mã vạch Mailmark trong C#, hướng dẫn này sẽ chỉ ra các bước cụ thể. Bạn sẽ thấy cách cấu hình X‑dimension và chiều cao thanh, sau đó lưu mã vạch dưới dạng ảnh PNG mà không cần công cụ bổ sung.

Việc tạo mã vạch bưu chính là một nhiệm vụ thường gặp khi xây dựng phần mềm nhãn thư, nhưng kích thước mặc định thường không phù hợp với máy in hoặc yêu cầu bố cục. Khi kết thúc tutorial này, bạn sẽ có thể kiểm soát kích thước mã vạch một cách chính xác và tạo ra hai loại Mailmark hợp lệ (kiểu C và kiểu L) sẵn sàng để in.

**Bạn sẽ học được**

* Cách đặt X‑dimension (độ rộng mô-đun) và chiều cao thanh cho một `BarcodeGenerator`.
* Cách lưu mã vạch đã tạo thành file PNG bằng `BarCodeImageFormat`.
* Những lỗi thường gặp như đường dẫn thư mục không hợp lệ hoặc giá trị kích thước không được hỗ trợ.
* Mẹo tái sử dụng cùng một cấu hình cho nhiều mã vạch.

## Yêu cầu trước

* .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.6+).
* Gói NuGet **Aspose.BarCode for .NET** (hoặc bất kỳ thư viện tương thích nào cung cấp `BarcodeGenerator`, `EncodeTypes` và `BarCodeImageFormat`).
* Kiến thức cơ bản về cú pháp C# và I/O file.

> **Mẹo chuyên nghiệp:** Cài đặt gói bằng lệnh CLI  
> `dotnet add package Aspose.BarCode` để giữ dự án của bạn gọn gàng.

## Bước 1: Xác định thư mục đầu ra

Trước khi tạo bất kỳ mã vạch nào, bạn phải quyết định nơi các file PNG sẽ được ghi. Sử dụng đường dẫn tuyệt đối giúp tránh bất ngờ trên các máy khác nhau.

```csharp
// Step 1: Define the folder where the barcode images will be saved
string outputFolder = @"C:\Temp\Barcodes\";

// Ensure the directory exists; create it if necessary
if (!Directory.Exists(outputFolder))
{
    Directory.CreateDirectory(outputFolder);
}
```

*Lý do quan trọng*: Nếu thư mục không tồn tại, `Save` sẽ ném `IOException`. Lệnh `Directory.CreateDirectory` là idempotent — nó không làm gì nếu thư mục đã tồn tại.

## Bước 2: Tạo mã vạch Mailmark kiểu C và **đặt kích thước**

Mailmark kiểu C mã hoá một chuỗi alphanumeric 20 ký tự. Sau khi khởi tạo generator, bạn có thể **đặt kích thước** thông qua đối tượng `Parameters.Barcode`.

```csharp
// Step 2: Create a Mailmark C‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkC = new BarcodeGenerator(EncodeTypes.Mailmark, "21B2254800659JW5O9QA6Y");

// Set the width of a single module (X‑dimension) to 4 pixels
mailmarkC.Parameters.Barcode.XDimension.Pixels = 4;

// Set the overall bar height to 50 pixels
mailmarkC.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the image; the second argument specifies PNG format
mailmarkC.Save($"{outputFolder}PostalMailmarkCType.png", BarCodeImageFormat.Png);
```

### Tại sao chọn các giá trị này?

* **X‑dimension** kiểm soát độ rộng của thanh nhỏ nhất (một “mô-đun”). Giá trị `4` pixel tạo ra mã vạch dễ đọc bởi hầu hết các máy in laser đồng thời giữ kích thước file ở mức vừa phải.
* **BarHeight** xác định kích thước dọc của các thanh. `50` pixel là chiều cao phổ biến cho nhãn thư tiêu chuẩn, nhưng bạn có thể tăng lên cho các định dạng lớn hơn.

> **Trường hợp đặc biệt:** Một số máy in yêu cầu chiều cao thanh tối thiểu là 30 px. Đặt chiều cao thấp hơn khả năng của máy in có thể gây ra mã vạch không đọc được.

## Bước 3: Tạo mã vạch Mailmark kiểu L và **đặt kích thước**

Kiểu L sử dụng chuỗi dữ liệu dài hơn (tối đa 30 ký tự). Cách đặt kích thước tương tự được áp dụng.

```csharp
// Step 3: Create a Mailmark L‑type barcode, configure its size, and save it as PNG
BarcodeGenerator mailmarkL = new BarcodeGenerator(EncodeTypes.Mailmark, "41038422416563762EF61AH8T");

// Reuse the same dimension settings for consistency
mailmarkL.Parameters.Barcode.XDimension.Pixels = 4;
mailmarkL.Parameters.Barcode.BarHeight.Pixels = 50;

// Save the L‑type barcode image
mailmarkL.Save($"{outputFolder}PostalMailmarkLType.png", BarCodeImageFormat.Png);
```

### Tái sử dụng cấu hình

Nếu bạn tạo nhiều mã vạch với cùng kích thước, hãy cân nhắc tách cấu hình ra thành một phương thức trợ giúp:

```csharp
void ApplyStandardDimensions(BarcodeGenerator generator)
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.BarHeight.Pixels = 50;
}
```

Gọi `ApplyStandardDimensions(mailmarkC)` và `ApplyStandardDimensions(mailmarkL)` giảm thiểu việc lặp lại và giúp các thay đổi trong tương lai (ví dụ: chuyển sang mô-đun 5 pixel) chỉ cần chỉnh một dòng.

## Bước 4: Kiểm tra các file PNG đã tạo

Sau khi chạy chương trình, mở hai file PNG trong bất kỳ trình xem ảnh nào. Bạn sẽ thấy hai mã vạch Mailmark riêng biệt, mỗi mô-đun 4 px và chiều cao 50 px.

*Kết quả mong đợi*

| Tên file                     | Kích thước xấp xỉ (px) |
|------------------------------|------------------------|
| `PostalMailmarkCType.png`    | 4 px × module × N modules |
| `PostalMailmarkLType.png`    | 4 px × module × N modules |

Chiều rộng chính xác phụ thuộc vào độ dài dữ liệu đã mã hoá, nhưng chiều cao sẽ luôn là **50 px** vì chúng ta đã đặt `BarHeight.Pixels`.

## Các lỗi thường gặp và cách tránh

| Vấn đề                              | Triệu chứng                                      | Cách khắc phục |
|-------------------------------------|--------------------------------------------------|----------------|
| Đường dẫn thư mục không hợp lệ      | `IOException: Could not find a part of the path`| Sử dụng `Path.Combine` với `Environment.SpecialFolder` hoặc kiểm tra chuỗi đường dẫn. |
| X‑dimension được đặt bằng 0 hoặc âm| Mã vạch xuất hiện như một khối đặc                | Đảm bảo `XDimension.Pixels` là số nguyên dương (tối thiểu 1). |
| `EncodeTypes.Mailmark` không được hỗ trợ | `ArgumentException` khi khởi tạo generator       | Xác nhận bạn đang dùng phiên bản mới nhất của thư viện Aspose.BarCode có hỗ trợ Mailmark. |
| Lưu với định dạng ảnh sai           | File PNG bị hỏng                                 | Dùng `BarCodeImageFormat.Png` (hoặc `Jpeg` nếu cần định dạng khác). |

## Mở rộng ví dụ

* **Kích thước khác** – Thay đổi `XDimension.Pixels` thành 3 để có mã vạch gọn hơn, hoặc tăng `BarHeight.Pixels` lên 70 cho nhãn lớn hơn.
* **Tạo hàng loạt** – Duyệt qua một tập hợp các chuỗi dữ liệu, áp dụng cùng cài đặt kích thước cho mỗi vòng lặp.
* **Định dạng ảnh khác** – Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg` hoặc `BarCodeImageFormat.Bmp` nếu quy trình làm việc của bạn yêu cầu.

## Kết luận

Bây giờ bạn đã biết **cách đặt kích thước** cho mã vạch Mailmark trong C# và xuất chúng dưới dạng file PNG. Bằng cách cấu hình `XDimension.Pixels` và `BarHeight.Pixels` bạn kiểm soát kích thước hiển thị của cả mã vạch kiểu C và kiểu L, đảm bảo chúng đáp ứng yêu cầu máy in và bố cục.  

Từ đây bạn có thể thử nghiệm các giá trị kích thước khác nhau, tích hợp mã vào hệ thống nhãn thư lớn hơn, hoặc tạo hàng loạt mã vạch cho các chiến dịch gửi thư bulk.

---

*Bước tiếp theo*: khám phá **kích thước BarcodeGenerator** cho QR code, hoặc đọc tài liệu Aspose.BarCode về **cài đặt DPI** cho in độ phân giải cao. Nếu cần nhúng mã vạch vào PDF, kết hợp cách này với thư viện **Aspose.PDF** để có giải pháp đầu‑cuối hoàn chỉnh.

## Bạn Nên Học Gì Tiếp Theo?


Các tutorial dưới đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm mã mẫu đầy đủ với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Set Border for ITF-14 Barcode Customization](/barcode/english/net/itf-14-barcode-customization/)
- [How to Configure Patch Code Barcodes with Aspose.BarCode for .NET](/barcode/english/net/patch-code-configuration/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}