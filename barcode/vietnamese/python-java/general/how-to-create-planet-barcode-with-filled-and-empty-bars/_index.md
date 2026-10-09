---
category: general
date: 2026-09-29
description: Tạo mã vạch planet trong C# với cả thanh đầy và thanh trống – hướng dẫn
  từng bước sử dụng Aspose.Barcode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode XDimension
- filled bars
- empty bars
- Aspose.Barcode C#
language: vi
lastmod: 2026-09-29
og_description: Tạo mã vạch hành tinh trong C# nhanh chóng. Tìm hiểu cách hiển thị
  các thanh đầy, chuyển sang các thanh rỗng và điều chỉnh kích thước X với Aspose.Barcode.
og_image_alt: 'Screenshot of two Planet barcodes: one with filled bars, one with empty
  bars'
og_title: Tạo mã vạch hành tinh với các thanh đầy và trống – Hướng dẫn C#
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  headline: How to create planet barcode with filled and empty bars
  type: TechArticle
- description: Create planet barcode in C# with both filled and empty bars – step‑by‑step
    guide using Aspose.Barcode.
  name: How to create planet barcode with filled and empty bars
  steps:
  - name: Changing the bar width
    text: If your label printer expects a different bar width, modify the `XDimension.Pixels`
      value. For high‑resolution printers, a value of **2** or **3** pixels may be
      preferable; for low‑resolution printers, **5** or **6** pixels can improve scan
      reliability.
  - name: Using a different image format
    text: Aspose.Barcode supports PNG, JPEG, BMP, GIF, and TIFF. Swap `BarCodeImageFormat.Png`
      with another enum value to match your downstream workflow.
  - name: Generating multiple barcodes in a loop
    text: When you need a batch of Planet barcodes (e.g., for a mailing list), wrap
      the generator logic in a `foreach` loop and change the data string each iteration.
  - name: Handling invalid input
    text: The Planet symbology accepts only numeric strings of **5‑8** digits. Supplying
      an invalid value throws an `ArgumentException`. Guard against this with a simple
      validation method.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cách tạo mã vạch hành tinh với các thanh đầy và trống
url: /vi/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch planet với các thanh đầy và trống

Nếu bạn cần **tạo mã vạch planet** dưới dạng hình ảnh trong C#, hướng dẫn này sẽ chỉ cho bạn cách tạo cả phiên bản thanh đầy và thanh trống. Bạn sẽ thấy cách đặt độ rộng của thanh (X‑dimension), bật/tắt thuộc tính `FilledBars`, và lưu kết quả dưới dạng tệp PNG—tất cả đều sử dụng thư viện Aspose.Barcode.

Việc tạo mã vạch bưu chính là yêu cầu phổ biến cho các hệ thống vận chuyển, ứng dụng danh sách gửi thư và bảng điều khiển logistics. Khi kết thúc hướng dẫn này, bạn sẽ có hai tệp PNG sẵn sàng sử dụng mà có thể nhúng vào báo cáo, email hoặc bản in.

## Yêu cầu trước

| Yêu cầu | Lý do quan trọng |
|-------------|----------------|
| .NET 6.0 hoặc sau này | Cung cấp môi trường chạy cho ví dụ C#. |
| Visual Studio 2022 (hoặc bất kỳ IDE C# nào) | Cho phép bạn biên dịch và chạy mã. |
| **Aspose.Barcode for .NET** NuGet package | Cung cấp lớp `BarcodeGenerator` và `EncodeTypes.Planet`. Cài đặt bằng `dotnet add package Aspose.Barcode`. |
| Quyền ghi vào một thư mục trên đĩa | Phương thức `Save` sẽ ghi các tệp PNG vào đường dẫn bạn chỉ định. |

## Bước 1: Thiết lập dự án và nhập không gian tên

Tạo một dự án console mới (hoặc thêm mã vào dự án hiện có) và tham chiếu không gian tên Aspose.Barcode.

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;
```

Các chỉ thị `using` này cho phép bạn truy cập vào `BarcodeGenerator`, `EncodeTypes` và các enum định dạng ảnh cần thiết cho hướng dẫn.

## Bước 2: Tạo mã vạch Planet với các thanh mặc định (đầy)

Mã vạch đầu tiên sử dụng cách hiển thị mặc định của thư viện, tức là các thanh được tô đầy.

```csharp
// Initialise a generator for the Planet (postal) barcode with sample data.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Optional: adjust the bar width (X dimension) to 4 pixels for clearer printing.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image with filled bars.
string filledPath = @"C:\Barcodes\PlanetFilledBars.png";
barcodeGenerator.Save(filledPath, BarCodeImageFormat.Png);

Console.WriteLine($"Filled Planet barcode saved to: {filledPath}");
```

**Tại sao cách này hoạt động:**  
`EncodeTypes.Planet` thông báo cho Aspose.Barcode sử dụng ký hiệu **Planet**, là một mã vạch bưu chính được USPS (United States Postal Service) sử dụng. Thuộc tính `XDimension` điều khiển độ rộng của mỗi thanh; đặt nó thành 4 pixel sẽ tạo ra mã vạch in tốt trên các máy in nhãn tiêu chuẩn. Mặc định, `FilledBars` là `true`, vì vậy các thanh xuất hiện đặc.

## Bước 3: Tạo mã vạch Planet với các thanh trống

Để tạo cùng dữ liệu với các thanh *trống*, bạn chỉ cần chuyển đổi cờ `FilledBars` trong khi giữ các cài đặt khác giống nhau.

```csharp
// Re‑use the same variable for clarity.
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for visual consistency.
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Render empty bars instead of filled ones.
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the image with empty bars.
string emptyPath = @"C:\Barcodes\PlanetEmptyBars.png";
barcodeGenerator.Save(emptyPath, BarCodeImageFormat.Png);

Console.WriteLine($"Empty Planet barcode saved to: {emptyPath}");
```

**Tại sao điều này quan trọng:**  
Một số hệ thống gửi thư yêu cầu kiểu **thanh trống** để cải thiện khả năng đọc khi mã vạch được in trên nền tối hoặc khi sử dụng màu tương phản. Bằng cách đặt `FilledBars = false`, trình tạo chỉ vẽ đường viền của các thanh, để phần bên trong trong suốt.

## Kết quả mong đợi

Sau khi chạy chương trình, thư mục `C:\Barcodes` (hoặc đường dẫn bạn đã chọn) sẽ chứa hai tệp PNG:

| Tệp | Mô tả hình ảnh |
|------|---------------------|
| `PlanetFilledBars.png` | Các thanh là hình chữ nhật đen đặc trên nền trắng. |
| `PlanetEmptyBars.png`  | Các thanh là đường viền đen; phần bên trong của mỗi thanh trong suốt (hiển thị nền). |

Cả hai hình ảnh đều mã hoá cùng chuỗi số `"123456"` và có độ rộng thanh 4 pixel, đảm bảo chúng trông nhất quán ngoại trừ kiểu tô.

## Các biến thể phổ biến và trường hợp đặc biệt

### Thay đổi độ rộng thanh

Nếu máy in nhãn của bạn yêu cầu độ rộng thanh khác, hãy sửa giá trị `XDimension.Pixels`. Đối với máy in độ phân giải cao, giá trị **2** hoặc **3** pixel có thể phù hợp hơn; đối với máy in độ phân giải thấp, **5** hoặc **6** pixel có thể cải thiện độ tin cậy khi quét.

```csharp
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 5; // example for coarse printers
```

### Sử dụng định dạng ảnh khác

Aspose.Barcode hỗ trợ PNG, JPEG, BMP, GIF và TIFF. Thay `BarCodeImageFormat.Png` bằng một giá trị enum khác để phù hợp với quy trình làm việc của bạn.

```csharp
barcodeGenerator.Save("Planet.tiff", BarCodeImageFormat.Tiff);
```

### Tạo nhiều mã vạch trong vòng lặp

Khi bạn cần một loạt mã vạch Planet (ví dụ: cho danh sách gửi thư), hãy bao bọc logic tạo mã trong một vòng lặp `foreach` và thay đổi chuỗi dữ liệu ở mỗi lần lặp.

```csharp
string[] postalCodes = { "123456", "654321", "112233" };
int index = 1;
foreach (var code in postalCodes)
{
    var gen = new BarcodeGenerator(EncodeTypes.Planet, code);
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    gen.Save($@"C:\Barcodes\Planet_{index}_filled.png", BarCodeImageFormat.Png);
    gen.Parameters.Barcode.FilledBars = false;
    gen.Save($@"C:\Barcodes\Planet_{index}_empty.png", BarCodeImageFormat.Png);
    index++;
}
```

### Xử lý đầu vào không hợp lệ

Ký hiệu Planet chỉ chấp nhận chuỗi số có **5‑8** chữ số. Cung cấp giá trị không hợp lệ sẽ ném ra `ArgumentException`. Hãy bảo vệ bằng một phương thức kiểm tra đơn giản.

```csharp
bool IsValidPlanet(string value) => System.Text.RegularExpressions.Regex.IsMatch(value, @"^\d{5,8}$");

string data = "ABC123";
if (!IsValidPlanet(data))
{
    Console.WriteLine("Invalid Planet data – must be 5 to 8 digits.");
    return;
}
```

## Mẹo chuyên nghiệp: Xác minh mã vạch bằng trình giả lập máy quét

Aspose.Barcode bao gồm lớp `BarcodeReader` mà bạn có thể dùng để xác nhận rằng hình ảnh đã tạo giải mã lại được dữ liệu gốc.

```csharp
using Aspose.Barcode.Reader;

// Verify filled barcode
using (BarCodeReader reader = new BarCodeReader(filledPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from filled image: {reader.GetCodeText()}");
}

// Verify empty barcode
using (BarCodeReader reader = new BarCodeReader(emptyPath, DecodeType.Planet))
{
    if (reader.Read())
        Console.WriteLine($"Decoded from empty image: {reader.GetCodeText()}");
}
```

Nếu đầu ra hiển thị `"123456"` cho cả hai tệp, mã vạch đã được tạo đúng.

## Kết luận

Bạn bây giờ đã biết cách **tạo mã vạch planet** dưới dạng hình ảnh trong C# với cả kiểu thanh đầy và thanh trống, kiểm soát **Planet barcode XDimension**, và lưu kết quả ở định dạng PNG bằng thư viện **Aspose.Barcode**. Điều chỉnh độ rộng thanh, chuyển đổi định dạng ảnh, hoặc lặp qua một tập hợp giá trị để phù hợp với bất kỳ quy trình mã bưu chính nào.

Tiếp theo, bạn có thể khám phá:

* **Thêm văn bản có thể đọc được** dưới mã vạch (`barcodeGenerator.Parameters.Caption.Show = true`).
* **Nhúng mã vạch vào tài liệu PDF** với Aspose.PDF.
* **Tạo các ký hiệu bưu chính khác** như **USPS POSTNET** hoặc **Intelligent Mail**.

Bạn có thể thoải mái thử nghiệm các tham số và tích hợp mã vào hệ thống vận chuyển hoặc gửi thư của mình. Chúc lập trình vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo Mã Vạch Planet trong C# – Hướng Dẫn Chi Tiết Từng Bước](/barcode/english/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/)
- [Tạo mã vạch planet trong C# – hướng dẫn lập trình đầy đủ](/barcode/english/python-java/general/create-planet-barcode-in-c-complete-programming-guide/)
- [Trình tạo mã vạch C# – tạo mã vạch Planet và ví dụ RM4SCC](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}