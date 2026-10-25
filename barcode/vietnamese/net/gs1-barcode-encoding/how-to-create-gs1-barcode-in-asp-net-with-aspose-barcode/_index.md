---
category: general
date: 2026-10-24
description: Học cách tạo mã vạch GS1 trong ASP.NET bằng Aspose.BarCode. Hướng dẫn
  từng bước để tạo mã vạch từ chuỗi và xuất ra PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to create GS1 barcode
- generate barcode from string
- barcode generator asp.net
- create barcode with aspose
language: vi
lastmod: 2026-10-24
og_description: Cách tạo mã vạch GS1 trong ASP.NET bằng Aspose.BarCode. Thực hiện
  theo hướng dẫn này để tạo mã vạch từ chuỗi, cấu hình các thiết lập hiển thị và lưu
  file PNG.
og_image_alt: Screenshot of a generated GS1 Micro PDF417 barcode saved as PNG
og_title: Cách tạo mã vạch GS1 trong ASP.NET – hướng dẫn đầy đủ của Aspose
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  headline: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  type: TechArticle
- description: Learn how to create GS1 barcode in ASP.NET using Aspose.BarCode. Step‑by‑step
    guide to generate barcode from string and render PNG.
  name: How to create GS1 barcode in ASP.NET with Aspose.BarCode
  steps:
  - name: 4.1 Prepare the GS1 data string
    text: 'GS1 data must be wrapped in parentheses with the AI code. For a product
      identifier (01) and a batch number (10) the string looks like:'
  - name: 4.2 Build the GS1 Micro PDF417 generator
    text: '```csharp public static byte[] GenerateGs1MicroPdf417(string gs1Data, string
      outputFolder) { // Step 4.2.1: Create a generator for Micro PDF417 using the
      GS1 data. BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417,
      gs1Data);'
  - name: 4.3 Expose the generator through an ASP.NET endpoint
    text: '```csharp app.MapGet("/gs1barcode", (HttpContext context) => { string outputFolder
      = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes"); Directory.CreateDirectory(outputFolder);
      // Ensure the folder exists'
  type: HowTo
tags:
- Aspose.BarCode
- GS1
- ASP.NET
- C#
title: Cách tạo mã vạch GS1 trong ASP.NET với Aspose.BarCode
url: /vi/net/gs1-barcode-encoding/how-to-create-gs1-barcode-in-asp-net-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch GS1 trong ASP.NET với Aspose.BarCode

Nếu bạn cần **cách tạo mã vạch GS1** trong một ứng dụng ASP.NET, hướng dẫn này sẽ cho bạn các bước chính xác. Bạn sẽ thấy cách tạo mã vạch từ một chuỗi, cấu hình giao diện hiển thị, và lưu kết quả dưới dạng ảnh PNG.

Việc tạo mã vạch GS1 không yêu cầu logic mã hoá tùy chỉnh. Bằng cách sử dụng Aspose.BarCode, bạn sẽ có một giải pháp đáng tin cậy, tuân thủ tiêu chuẩn, hoạt động trên .NET 6+ và các framework trước đó. Hướng dẫn này bao gồm mọi thứ từ thiết lập dự án đến kiểm tra đầu ra, vì vậy bạn có thể sao chép mã trực tiếp vào dự án web của mình.

## Yêu cầu trước

* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ .NET)
* .NET 6 SDK (hoặc .NET Framework 4.7.2 trở lên)
* Kiến thức cơ bản về ASP.NET Core hoặc ASP.NET Framework
* Giấy phép Aspose.BarCode (phiên bản dùng thử miễn phí hoạt động cho việc thử nghiệm)

Không cần thư viện bên thứ ba nào khác vì Aspose.BarCode xử lý toàn bộ việc mã hoá và render nội bộ.

## Bước 1: Tạo dự án ASP.NET mới

Mở Visual Studio và tạo một **ASP.NET Core Web App** (chọn mẫu *Empty*). Đối với dự án Web Forms cổ điển, cùng một đoạn mã vẫn hoạt động trong file code‑behind.

```csharp
// Program.cs (ASP.NET Core minimal API example)
using Microsoft.AspNetCore.Builder;
using Microsoft.Extensions.Hosting;

var builder = WebApplication.CreateBuilder(args);
var app = builder.Build();

app.MapGet("/", () => "GS1 barcode generator is ready.");
app.Run();
```

Chạy dự án sẽ hiển thị *GS1 barcode generator is ready.* trong trình duyệt. Điều này xác nhận rằng web host đang hoạt động.

## Bước 2: Cài đặt Aspose.BarCode qua NuGet

Mở **Package Manager Console** và chạy:

```powershell
Install-Package Aspose.BarCode
```

Gói này sẽ thêm namespace `Aspose.BarCode.Generation`, chứa lớp `BarcodeGenerator` mà bạn sẽ dùng để **generate barcode from string**. Lệnh NuGet cũng sẽ cập nhật file dự án với tham chiếu cần thiết.

## Bước 3: Tạo mã vạch đơn giản từ một chuỗi

Để minh họa cách sử dụng cơ bản, tạo một phương thức trợ giúp trả về mảng byte PNG. Phương thức này có thể được gọi từ controller, Razor page, hoặc bất kỳ endpoint nào.

```csharp
using Aspose.BarCode.Generation;
using System.IO;

/// <summary>
/// Generates a barcode image from the supplied text.
/// </summary>
/// <param name="text">The data to encode.</param>
/// <param name="encodeType">The barcode symbology.</param>
/// <returns>PNG image bytes.</returns>
public static byte[] GenerateBarcode(string text, EncodeTypes encodeType)
{
    // Step 3.1: Initialize the generator with the desired symbology and data.
    BarcodeGenerator generator = new BarcodeGenerator(encodeType, text);

    // Step 3.2: Set a modest module width – 2 pixels gives a clear image.
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 3.3: Render the barcode to a memory stream in PNG format.
    using MemoryStream ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return ms.ToArray();
}
```

Bây giờ bạn có thể gọi `GenerateBarcode("HelloWorld", EncodeTypes.Code128)` từ bất kỳ endpoint nào và ghi các byte kết quả vào phản hồi HTTP. Điều này minh họa mẫu **barcode generator asp.net** cho các chuỗi tùy ý.

## Bước 4: Cách tạo mã vạch GS1 – Ví dụ Micro PDF417

Mã vạch GS1 nhúng các application‑identifiers (AIs) truyền tải thông tin sản phẩm. Aspose.BarCode hỗ trợ biến thể tương thích GS1 của Micro PDF417, lý tưởng cho việc biểu diễn dữ liệu gọn nhẹ.

### 4.1 Chuẩn bị chuỗi dữ liệu GS1

Dữ liệu GS1 phải được bao quanh bằng dấu ngoặc đơn cùng với mã AI. Đối với mã định danh sản phẩm (01) và số lô (10), chuỗi sẽ như sau:

```csharp
string gs1Data = "(01)12345678901234(10)ABCD";
```

Dấu ngoặc đơn là một phần của tiêu chuẩn; Aspose.BarCode sẽ tự động phân tích chúng.

### 4.2 Xây dựng trình tạo GS1 Micro PDF417

```csharp
public static byte[] GenerateGs1MicroPdf417(string gs1Data, string outputFolder)
{
    // Step 4.2.1: Create a generator for Micro PDF417 using the GS1 data.
    BarcodeGenerator gs1Generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, gs1Data);

    // Step 4.2.2: Apply the same visual settings used for other barcodes.
    gs1Generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Step 4.2.3: Micro PDF417 allows 1‑4 columns; 4 gives a more square shape.
    gs1Generator.Parameters.Barcode.Pdf417.Columns = 4;

    // Step 4.2.4: Save the image to the specified folder.
    string filePath = Path.Combine(outputFolder, "GS1MicroPdf417.png");
    gs1Generator.Save(filePath, BarCodeImageFormat.Png);

    // Return the file bytes for immediate HTTP response if needed.
    return File.ReadAllBytes(filePath);
}
```

### 4.3 Phơi bày trình tạo qua endpoint ASP.NET

```csharp
app.MapGet("/gs1barcode", (HttpContext context) =>
{
    string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "wwwroot", "barcodes");
    Directory.CreateDirectory(outputFolder); // Ensure the folder exists

    byte[] pngBytes = GenerateGs1MicroPdf417("(01)12345678901234(10)ABCD", outputFolder);

    context.Response.ContentType = "image/png";
    return context.Response.Body.WriteAsync(pngBytes, 0, pngBytes.Length);
});
```

Truy cập `https://localhost:5001/gs1barcode` hiện sẽ truyền PNG đã tạo. Hình ảnh tuân theo tiêu chuẩn GS1, và file cũng được lưu trên đĩa để sử dụng sau.

## Bước 5: Render các loại mã vạch bổ sung

Cách tiếp cận **create barcode with aspose** tương tự hoạt động cho các symbology khác. Dưới đây là một ví dụ nhanh tạo QR code từ một URL:

```csharp
byte[] qrBytes = GenerateBarcode("https://example.com", EncodeTypes.QR);
File.WriteAllBytes(Path.Combine(outputFolder, "ExampleQR.png"), qrBytes);
```

Bạn có thể thay `EncodeTypes.QR` bằng `EncodeTypes.Code128`, `EncodeTypes.DataMatrix`, hoặc bất kỳ loại nào được hỗ trợ. Các tham số hiển thị (`XDimension`, `Resolution`, `Color`) có thể cấu hình qua đối tượng `Parameters`.

## Bước 6: Những lỗi thường gặp và mẹo thực hành tốt

| Vấn đề | Nguyên nhân | Cách tránh |
|-------|----------------|-----------------|
| **Định dạng AI không đúng** | Thiếu dấu ngoặc hoặc độ dài AI sai gây lỗi mã hoá. | Luôn xây dựng chuỗi GS1 đúng theo tiêu chuẩn. Sử dụng phương thức trợ giúp để nối các AI. |
| **Quá nhiều cột** | Micro PDF417 chỉ hỗ trợ 1‑4 cột; đặt 5 sẽ gây ra ngoại lệ. | Kiểm tra giá trị cột trước khi gán: `if (columns < 1 || columns > 4) throw …` |
| **Độ phân giải ảnh thấp** | Giá trị `XDimension` quá nhỏ có thể làm mã vạch không đọc được trên máy in. | Đối với mã vạch chuẩn in, tăng `Resolution` (ví dụ, `generator.Parameters.Image.Resolution = 300`). |
| **Vấn đề đường dẫn file trên Linux** | Dấu gạch chéo ngược được mã hoá cứng sẽ gây lỗi trên môi trường không phải Windows. | Sử dụng `Path.Combine` để xây dựng đường dẫn file; nó sẽ xử lý dấu phân cách theo hệ điều hành. |
| **Giấy phép chưa được áp dụng** | Phiên bản dùng thử miễn phí sẽ thêm watermark sau 30 ngày. | Áp dụng giấy phép sớm: `new License().SetLicense("Aspose.BarCode.lic");` |

## Bước 7: Xác minh mã vạch đã tạo

Sau khi chạy endpoint, mở file PNG bằng bất kỳ trình xem ảnh nào. Để xác nhận dữ liệu GS1 được mã hoá đúng, bạn có thể dùng một trình quét di động miễn phí hỗ trợ GS1 Micro PDF417 (nhiều ứng dụng quét mã vạch có liệt kê symbology này). Quét ảnh; ứng dụng sẽ trả về:

```
(01)12345678901234
(10)ABCD
```

Nếu trình quét báo lỗi, hãy kiểm tra lại định dạng AI và số cột.

## Kết luận

Bây giờ bạn đã biết **cách tạo mã vạch GS1** trong môi trường ASP.NET bằng Aspose.BarCode. Hướng dẫn đã bao gồm:

* Thiết lập dự án ASP.NET và cài đặt gói NuGet Aspose.BarCode.  
* Sử dụng **generate barcode from string** cho các mã vạch chung.  
* Thực hiện **create barcode with aspose** để tạo ảnh GS1‑compatible Micro PDF417.  
* Lưu ảnh vào đĩa và truyền nó qua endpoint HTTP.  

Từ đây bạn có thể khám phá các symbology GS1 khác (ví dụ, GS1 DataMatrix) hoặc tích hợp trình tạo vào quy trình xử lý đơn hàng lớn hơn. Thử nghiệm các giá trị `XDimension` khác nhau, màu sắc và mức sửa lỗi để phù hợp với thương hiệu và môi trường quét của bạn.

Chúc lập trình vui vẻ, và để ứng dụng của bạn nói ngôn ngữ toàn cầu của các mã vạch!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch code 128 với GS1 bằng Aspose.BarCode](/barcode/english/net/gs1-barcode-encoding/gs1-code-128-example/)
- [Cách tạo vùng yên tĩnh (Quiet Zone) cho mã vạch ITF-14 bằng Aspose.BarCode cho .NET](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)
- [Cách tạo mã vạch ITF-14 .NET – Hướng dẫn toàn diện Aspose.BarCode Tutorials](/barcode/english/net/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}