---
category: general
date: 2026-11-14
description: Tìm hiểu cách tạo mã vạch PDF417 trong C# một cách nhanh chóng. Hướng
  dẫn này cũng chỉ ra cách tạo PDF417 và cách tùy chỉnh các thiết lập PDF417 để kiểm
  soát chính xác.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417
- how to customize pdf417
language: vi
lastmod: 2026-11-14
og_description: Tạo mã vạch PDF417 trong C# với hướng dẫn từng bước. Tìm hiểu cách
  tạo PDF417 và cách tùy chỉnh các tham số PDF417 để đạt kết quả chính xác.
og_image_alt: Screenshot showing a generated PDF417 barcode created with C# code
og_title: Tạo mã vạch PDF417 trong C# – hướng dẫn đầy đủ với bố cục tùy chỉnh
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  headline: How to create PDF417 barcode with custom layout in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# quickly. This guide also shows
    how to generate PDF417 and how to customize PDF417 settings for precise control.
  name: How to create PDF417 barcode with custom layout in C#
  steps:
  - name: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
    text: '**Check dimensions:** Ensure columns/rows stay within the allowed range.'
  - name: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
    text: '**Adjust error level:** Increase `ErrorLevel` for damaged media.'
  - name: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
    text: '**Review image quality:** Save with a higher DPI (`generator.Save(outputPath,
      BarCodeImageFormat.Png, 300)`) if you plan to print.'
  type: HowTo
tags:
- barcode
- pdf417
- C#
title: Cách tạo mã vạch PDF417 với bố cục tùy chỉnh trong C#
url: /vi/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-custom-layout-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 với bố cục tùy chỉnh trong C#

Nếu bạn cần **tạo mã vạch pdf417** cho hệ thống vé, thẻ tồn kho, hoặc quét trong ứng dụng di động, hướng dẫn này sẽ chỉ cho bạn quy trình hoàn chỉnh. Bạn sẽ thấy cách tạo PDF417 nhanh chóng và cách tùy chỉnh các thiết lập PDF417 như số cột và hàng, để mã vạch phù hợp với các ràng buộc thiết kế của bạn.

Việc tạo mã vạch không đòi hỏi một thư viện đồ họa phức tạp—chỉ cần Aspose.BarCode cho .NET (hoặc bất kỳ API tương thích nào). Khi kết thúc hướng dẫn, bạn sẽ có một tệp PNG sẵn sàng để nhúng vào PDF, trang web, hoặc in trực tiếp từ ứng dụng của mình.

## Yêu cầu trước

- .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+)
- Aspose.BarCode cho .NET (gói NuGet `Aspose.BarCode`)
- Kiến thức cơ bản về C# và Visual Studio (hoặc bất kỳ IDE nào)

> **Pro tip:** Nếu bạn đang sử dụng pipeline CI/CD, hãy thêm tham chiếu gói NuGet vào tệp dự án để các bản dựng luôn có thể tái tạo.

## Bước 1: Cài đặt thư viện mã vạch

Mở thư mục dự án của bạn trong terminal và chạy:

```bash
dotnet add package Aspose.BarCode
```

Gói này bao gồm lớp `BarcodeGenerator` được sử dụng xuyên suốt tutorial. Không cần bất kỳ phụ thuộc gốc nào khác.

## Bước 2: Tạo mã vạch PDF417 cơ bản

Mục tiêu đầu tiên là **tạo pdf417 barcode** với các thiết lập mặc định. Chương trình dưới đây thiết lập bộ tạo, mã hoá một chuỗi mẫu, và lưu kết quả dưới dạng ảnh PNG.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417Demo
{
    static void Main()
    {
        // Step 2.1: Initialise the generator for PDF417 with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample text for PDF417");

        // Step 2.2: Save the barcode as PNG
        string outputPath = "Pdf417Default.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

**Tại sao cách này hoạt động:**  
`EncodeTypes.Pdf417` báo cho thư viện sử dụng ký hiệu PDF417. Hàm khởi tạo tự động tạo một đối tượng `Barcode` với các giá trị cột/hàng mặc định, đảm bảo khả năng quét cho hầu hết các trường hợp sử dụng.

Chạy chương trình (`dotnet run`). Bạn sẽ thấy `Pdf417Default.png` trong thư mục dự án. Mở ảnh sẽ hiển thị một mã vạch PDF417 tiêu chuẩn, sẵn sàng để quét.

![Ví dụ tạo mã vạch PDF417](https://example.com/images/pdf417-default.png){:alt="Ví dụ tạo mã vạch PDF417 hiển thị bố cục mặc định"}

## Bước 3: Cách tạo PDF417 với kích thước tùy chỉnh

Đôi khi một nhãn có kích thước cố định hoặc một thành phần UI yêu cầu một diện tích mã vạch nhất định. Đó là lúc **cách tạo pdf417** với các cột và hàng tùy chỉnh trở nên quan trọng.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Pdf417CustomDemo
{
    static void Main()
    {
        // Initialise generator with the same text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Custom layout text");

        // ---- Customization begins here ----
        // Set the number of columns (2‑30). Fewer columns make the barcode taller.
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Set the number of rows (1‑90). More rows make the barcode wider.
        generator.Parameters.Barcode.Pdf417.Rows = 9;
        // ------------------------------------

        // Save the customized barcode
        string outputPath = "Pdf417CustomLayout.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Custom barcode saved to {outputPath}");
    }
}
```

**Lý do bạn có thể muốn làm như vậy:**  
- **Chiều rộng hạn chế:** Giảm số cột và tăng số hàng tạo ra một mã vạch rộng hơn nhưng ngắn hơn, phù hợp cho nhãn hẹp.  
- **Chiều cao hạn chế:** Tăng số cột và giảm số hàng tạo ra một mã vạch cao hơn, hẹp hơn, hữu ích khi bạn có không gian dọc.

Cả `Columns` và `Rows` chỉ chấp nhận các giá trị trong phạm vi tài liệu (2‑30 cho cột, 1‑90 cho hàng). Việc cung cấp giá trị ngoài phạm vi sẽ ném ra `ArgumentOutOfRangeException`, vì vậy luôn xác thực đầu vào người dùng nếu bạn hiển thị các thiết lập này trong UI.

## Bước 4: Cách tùy chỉnh PDF417 thêm nữa

Ngoài cột và hàng, ký hiệu PDF417 còn cung cấp nhiều tham số tùy chọn:

| Thuộc tính | Mục đích | Giá trị điển hình |
|------------|----------|-------------------|
| `ErrorLevel` | Kiểm soát khả năng sửa lỗi | 0‑8 (cao hơn = mạnh hơn) |
| `MacroPdf417` | Bật macro PDF417 cho dữ liệu đa đoạn | `true`/`false` |
| `CompactPdf417` | Tạo mã vạch gọn hơn với chi phí giảm khả năng sửa lỗi | `true`/`false` |
| `SecurityLevel` | Thêm chữ số kiểm tra bảo mật | 0‑2 |

Dưới đây là một ví dụ nhanh cũng đặt mức lỗi tối đa (8) cho môi trường có nhiễu:

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 8;
generator.Parameters.Barcode.Pdf417.CompactPdf417 = true;
```

**Tại sao điều này quan trọng:**  
Khả năng sửa lỗi cao cho phép máy quét khôi phục dữ liệu ngay cả khi một phần mã vạch bị hỏng. Tuy nhiên, nó cũng làm tăng kích thước mã vạch, vì vậy hãy cân bằng thiết lập này với các ràng buộc bố cục của bạn.

## Bước 5: Xác minh mã vạch hoạt động

Sau khi tạo PNG, hãy thử nghiệm với bất kỳ ứng dụng quét mã vạch nào (hầu hết smartphone đều có trình đọc PDF417 miễn phí). Nếu máy quét trả về văn bản gốc (`Custom layout text`), mã vạch là hợp lệ.

Nếu gặp vấn đề khi quét:

1. **Kiểm tra kích thước:** Đảm bảo cột/hàng nằm trong phạm vi cho phép.  
2. **Điều chỉnh mức lỗi:** Tăng `ErrorLevel` cho phương tiện bị hỏng.  
3. **Xem lại chất lượng ảnh:** Lưu với DPI cao hơn (`generator.Save(outputPath, BarCodeImageFormat.Png, 300)`) nếu bạn dự định in.

## Mã nguồn đầy đủ cho một helper có thể tái sử dụng

Dưới đây là một lớp gọn, có thể tái sử dụng mà bạn có thể đưa vào bất kỳ dự án .NET nào. Nó gói gọn **cách tạo pdf417** và **cách tùy chỉnh pdf417** trong một phương thức duy nhất.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

public static class Pdf417Helper
{
    /// <summary>
    /// Creates a PDF417 barcode image with optional layout parameters.
    /// </summary>
    /// <param name="text">The data to encode.</param>
    /// <param name="outputPath">Full file path for the PNG output.</param>
    /// <param name="columns">Number of columns (2‑30). Pass null to use default.</param>
    /// <param name="rows">Number of rows (1‑90). Pass null to use default.</param>
    /// <param name="errorLevel">Error correction level (0‑8). Null = default.</param>
    public static void CreatePdf417(string text, string outputPath,
                                    int? columns = null,
                                    int? rows = null,
                                    int? errorLevel = null)
    {
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

        // Apply optional customizations
        if (columns.HasValue) generator.Parameters.Barcode.Pdf417.Columns = columns.Value;
        if (rows.HasValue)    generator.Parameters.Barcode.Pdf417.Rows    = rows.Value;
        if (errorLevel.HasValue) generator.Parameters.Barcode.Pdf417.ErrorLevel = errorLevel.Value;

        // Save as high‑resolution PNG (300 DPI) for printing scenarios
        generator.Save(outputPath, BarCodeImageFormat.Png, 300);
    }
}
```

Bạn có thể gọi helper này như sau:

```csharp
Pdf417Helper.CreatePdf417(
    text: "Order #12345",
    outputPath: "OrderBarcode.png",
    columns: 5,
    rows: 12,
    errorLevel: 6);
```

Phương thức này trừu tượng hoá phần boiler‑plate lặp đi lặp lại, cho phép bạn tập trung vào logic nghiệp vụ.

## Những lỗi thường gặp và cách tránh chúng

- **Giá trị ngoài phạm vi:** Luôn xác thực `columns` và `rows` trước khi gán.  
- **Định dạng ảnh không đúng:** Một số máy quét cũ chỉ chấp nhận BMP hoặc JPEG. Dùng `BarCodeImageFormat.Bmp` nếu cần.  
- **DPI thấp cho in:** DPI mặc định là 96. Đối với in chất lượng cao, hãy đặt DPI cao hơn (ví dụ, 300) khi gọi `Save`.  
- **Thiếu hỗ trợ phông chữ:** PDF417 mã hoá dữ liệu nhị phân, vì vậy thường không cần chỉ định phông chữ. Tuy nhiên, nếu bạn phủ lên văn bản trên ảnh, hãy chắc chắn phông chữ đã được cài đặt trên máy đích.

## Kết luận

Bạn đã biết cách **tạo pdf417 barcode** từ đầu đến cuối, cách **tạo pdf417** với các thiết lập cột/hàng tùy chỉnh, và cách **tùy chỉnh pdf417** cho sửa lỗi và độ gọn. Bằng cách áp dụng mẫu helper có thể tái sử dụng, bạn có thể tạo mã vạch theo yêu cầu, điều chỉnh chúng cho bất kỳ ràng buộc bố cục nào và đảm bảo quét ổn định trong môi trường sản xuất.

**Các bước tiếp theo**

- Khám phá các ký hiệu khác như QR hoặc Code128 bằng cùng lớp `BarcodeGenerator`.  
- Kết hợp đầu ra PNG với thư viện tạo PDF (ví dụ, iText7) để nhúng mã vạch vào hoá đơn.  
- Thử nghiệm `MacroPdf417` cho truyền dữ liệu đa đoạn, một tính năng hữu ích trong logistics và vận tải.

Chúc bạn lập trình vui vẻ, và hy vọng mã vạch của bạn luôn quét được ngay lần đầu!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate barcode and customize PDF417 barcode in C#](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/)
- [How to create PDF417 barcode and export PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-export-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}