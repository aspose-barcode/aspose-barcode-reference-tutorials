---
category: general
date: 2026-08-22
description: Tạo mã vạch FCC 11 bằng C# sử dụng Aspose.BarCode. Học cách viết mã từng
  bước, cấu hình kích thước và tạo hình ảnh PNG cho Australia Post.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create fcc 11 barcode
- Australia Post barcode
- Aspose.BarCode C#
- FCC 59 barcode
- FCC 62 barcode
- N‑Table encoding
- C‑Table encoding
language: vi
lastmod: 2026-08-22
og_description: Tạo mã vạch FCC 11 bằng C# với Aspose.BarCode. Tham khảo hướng dẫn
  ngắn gọn này để tạo mã vạch PNG cho Australia Post, bao gồm các biến thể FCC 59
  và FCC 62.
og_image_alt: Screenshot showing a generated FCC 11 barcode image
og_title: Tạo mã vạch FCC 11 trong C# – hướng dẫn đầy đủ Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  headline: How to create FCC 11 barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Create FCC 11 barcode in C# using Aspose.BarCode. Learn step‑by‑step
    code, configure dimensions, and generate PNG images for Australia Post.
  name: How to create FCC 11 barcode in C# with Aspose.BarCode
  steps:
  - name: 4.1 FCC 59 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)'
  - name: 4.2 FCC 62 with N‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)'
  - name: 4.3 FCC 62 with C‑Table encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix'
  - name: 4.4 FCC 62 with Other encoding
    text: '```csharp barcodeGenerator = new BarcodeGenerator( EncodeTypes.AustraliaPost,
      "6201234567321032103210"); // Long payload for "Other" table'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- AustraliaPost
title: Cách tạo mã vạch FCC 11 trong C# với Aspose.BarCode
url: /vi/python-java/general/how-to-create-fcc-11-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch FCC 11 trong C# với Aspose.BarCode

Nếu bạn cần **tạo mã vạch FCC 11** trong một ứng dụng .NET, hướng dẫn này sẽ cho bạn thấy đoạn mã chính xác cần thiết. Bạn sẽ thấy cách cấu hình kích thước mã vạch, chọn bảng mã hóa phù hợp, và lưu kết quả dưới dạng tệp PNG.

Việc tạo mã vạch Australia Post là yêu cầu phổ biến cho logistics, hệ thống gửi thư và theo dõi tồn kho. Bài hướng dẫn này đề cập đến định dạng FCC 11 và cũng trình bày cách tạo mã vạch FCC 59 và FCC 62 với các bảng mã hóa khác nhau, để bạn có thể tái sử dụng cùng mẫu cho các dịch vụ bưu chính khác.

## Những gì bạn cần

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ C#)  
* Giấy phép hợp lệ cho **Aspose.BarCode for .NET** – phiên bản community hoạt động cho mục đích đánh giá  
* Quyền ghi vào thư mục nơi các tệp PNG sẽ được lưu  

Những yêu cầu này đảm bảo rằng mã có thể biên dịch và chạy mà không cần cấu hình bổ sung.

## Bước 1: Cài đặt gói NuGet Aspose.BarCode

Mở terminal trong thư mục dự án và chạy:

```bash
dotnet add package Aspose.BarCode
```

Lệnh này sẽ thêm phiên bản ổn định mới nhất của thư viện vào tệp dự án của bạn. Gói này chứa lớp `BarcodeGenerator` được sử dụng xuyên suốt trong hướng dẫn này.

## Bước 2: Xác định thư mục đầu ra

Tạo một thư mục để lưu các hình ảnh được tạo. Đường dẫn có thể là tuyệt đối hoặc tương đối so với tệp thực thi.

```csharp
// Step 2: Define the output folder
string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputPath);
```

`Directory.CreateDirectory` đảm bảo thư mục tồn tại, ngăn ngừa lỗi thời gian chạy khi phương thức `Save` ghi tệp.

## Bước 3: Tạo mã vạch FCC 11

Định dạng FCC 11 là mã hóa mặc định cho các mã vạch bưu điện của Australia Post. Đoạn mã dưới đây tạo một mã vạch mã hoá chuỗi số `1101234567`.

```csharp
// Step 3: Create a BarcodeGenerator for FCC 11
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,      // Use the Australia Post symbology
    "1101234567");                  // Data for FCC 11

// Configure visual appearance
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;   // Width of a single module
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50; // Height of the barcode

// Save as PNG
string fcc11Path = Path.Combine(outputPath, "PostalAustraliaPostFCC11.png");
barcodeGenerator.Save(fcc11Path, BarCodeImageFormat.Png);
```

**Tại sao cách này hoạt động:**  
* `EncodeTypes.AustraliaPost` chỉ cho thư viện áp dụng các quy tắc mã hóa của Australia Post.  
* Chuỗi dữ liệu `1101234567` tuân theo đặc tả FCC 11: hai chữ số đầu tiên (`11`) xác định định dạng, tiếp theo là mã khách hàng 7 chữ số.  
* `XDimension` và `BarHeight` kiểm soát kích thước của mã vạch đã in, điều này quan trọng để máy quét đọc được.

Sau khi chạy chương trình, bạn sẽ thấy tệp `PostalAustraliaPostFCC11.png` trong thư mục `Barcodes`. Hình ảnh trông như sau:

![create fcc 11 barcode example](https://example.com/fcc11.png "FCC 11 barcode generated by Aspose.BarCode")

## Bước 4: Tạo các mã vạch Australia Post bổ sung (tùy chọn)

Mặc dù mục tiêu chính là **tạo mã vạch FCC 11**, bạn thường cần các mã vạch FCC 59 hoặc FCC 62 cho các lớp thư khác nhau. Đoạn mã dưới đây tái sử dụng cùng một đối tượng `BarcodeGenerator`, chỉ thay đổi chuỗi dữ liệu và bảng mã hóa tùy chọn.

### 4.1 FCC 59 với mã hóa N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "590123456701234"); // FCC 59 data (prefix 59 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;

// Use N‑Table for customer information interpretation
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc59Path = Path.Combine(outputPath, "PostalAustraliaPostFCC59NTable.png");
barcodeGenerator.Save(fcc59Path, BarCodeImageFormat.Png);
```

### 4.2 FCC 62 với mã hóa N‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "620123456701234"); // FCC 62 data (prefix 62 + 13‑digit payload)

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.NTable;

string fcc62NPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62NTable.png");
barcodeGenerator.Save(fcc62NPath, BarCodeImageFormat.Png);
```

### 4.3 FCC 62 với mã hóa C‑Table

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567ASPOSE"); // FCC 62 data with alphanumeric suffix

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.CTable;

string fcc62CPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62CTable.png");
barcodeGenerator.Save(fcc62CPath, BarCodeImageFormat.Png);
```

### 4.4 FCC 62 với mã hóa Other

```csharp
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.AustraliaPost,
    "6201234567321032103210"); // Long payload for "Other" table

barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 50;
barcodeGenerator.Parameters.Barcode.AustralianPost.AustralianPostEncodingTable =
    CustomerInformationInterpretingType.Other;

string fcc62OtherPath = Path.Combine(outputPath, "PostalAustraliaPostFCC62OtherTable.png");
barcodeGenerator.Save(fcc62OtherPath, BarCodeImageFormat.Png);
```

Tất cả bốn hình ảnh được lưu cạnh nhau trong cùng một thư mục, giúp dễ dàng so sánh sự khác nhau về hình ảnh.

## Bước 5: Hiểu các bảng mã hóa

Australia Post định nghĩa ba bảng mã hóa:

* **N‑Table** – giải mã thông tin khách hàng dạng số. Sử dụng khi dữ liệu chỉ chứa các chữ số.  
* **C‑Table** – hỗ trợ ký tự alphanumeric, hữu ích cho các số tham chiếu có chứa chữ cái.  
* **Other** – dự phòng cho các định dạng dữ liệu tùy chỉnh hoặc mở rộng.

Việc chọn bảng đúng sẽ đảm bảo máy quét mã vạch giải mã thông tin chính xác như mong muốn. Nếu bạn bỏ qua thuộc tính `AustralianPostEncodingTable`, thư viện sẽ mặc định sử dụng N‑Table, có thể cắt bỏ các ký tự không phải số.

## Mẹo, trường hợp đặc biệt và những lỗi thường gặp

| Tình huống | Cách tiếp cận đề xuất |
|-----------|----------------------|
| Độ dài chuỗi dữ liệu ngắn hơn yêu cầu | Thêm các số 0 ở đầu phần số để đáp ứng đặc tả FCC. |
| Mã vạch bị mờ khi in | Tăng `XDimension` lên 5 hoặc 6 pixel và kiểm tra cài đặt DPI của máy in. |
| Máy quét trả về “định dạng không hợp lệ” | Xác minh rằng bảng mã hóa đúng (N‑Table, C‑Table, Other) phù hợp với dữ liệu. |
| Chạy trên Linux mà không có GUI | Đảm bảo gói `System.Drawing.Common` được tham chiếu, hoặc sử dụng phương thức `Save` với `BarCodeImageFormat.Png` không yêu cầu ngữ cảnh hiển thị. |
| Cần định dạng hình ảnh khác | Thay thế `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg` hoặc `BarCodeImageFormat.Tiff` theo yêu cầu. |

Những mẹo thực tế này xuất phát từ các triển khai thực tế của giải pháp mã vạch bưu điện.

## Ví dụ hoàn chỉnh có thể chạy được

Dưới đây là một chương trình tự chứa mà bạn có thể sao chép vào một dự án console mới (`dotnet new console`) và chạy mà không cần sửa đổi.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputPath = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputPath);

        // -------------------------------------------------
        // Create FCC 11 barcode – primary goal
        // -------------------------------------------------
        var fcc11 = new BarcodeGenerator(EncodeTypes.AustraliaPost, "1101234567");
        fcc11.Parameters.Barcode.XDimension.Pixels = 4;
        fcc11.Parameters.Barcode.BarHeight.Pixels = 50;
        fcc11


## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã đầy đủ, kèm theo giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch java – Mã vạch Australia Post với Aspose](/barcode/english/java/barcode-configuration/generating-australia-post-barcode/)
- [Tạo One-Dimensional Databar GS1 Encoding với Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/)
- [Cách tạo vùng yên tĩnh (quiet zone) cho mã Code 16K trong .NET bằng Aspose.BarCode](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}