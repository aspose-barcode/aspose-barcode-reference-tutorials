---
category: general
date: 2026-08-22
description: Tìm hiểu cách tạo mã vạch PDF417 trong C# với Aspose.BarCode, thiết lập
  kích thước mã vạch, điều chỉnh các cột và bật chế độ gọn.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- set barcode size
language: vi
lastmod: 2026-08-22
og_description: Tạo mã vạch PDF417 trong C# với Aspose.BarCode. Hướng dẫn này chỉ
  cách đặt kích thước mã vạch, kiểm soát số cột và bật chế độ compact để có hình ảnh
  nhỏ hơn.
og_image_alt: Screenshot of a generated PDF417 barcode in C# showing compact mode
og_title: Tạo mã vạch PDF417 trong C# – đặt kích thước, cột và chế độ nén
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate PDF417 barcode in C# with Aspose.BarCode, set
    barcode size, adjust columns, and enable compact mode.
  headline: How to generate PDF417 barcode in C# and set barcode size
  type: TechArticle
tags:
- pdf417
- barcode
- csharp
title: Cách tạo mã vạch PDF417 trong C# và đặt kích thước mã vạch
url: /vi/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-and-set-barcode-size/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 trong C# và đặt kích thước mã vạch

Nếu bạn cần **generate PDF417 barcode** trong một ứng dụng .NET, hướng dẫn này sẽ dẫn bạn qua toàn bộ quá trình. Bạn sẽ thấy chính xác **how to generate PDF417** với Aspose.BarCode, điều chỉnh **set barcode size**, và tạo một PNG nén có thể nhúng vào báo cáo hoặc ứng dụng di động.

Việc tạo mã vạch không yêu cầu một trình chỉnh sửa đồ họa riêng. Khi kết thúc tutorial này, bạn sẽ có một phương thức C# hoạt động đầy đủ, tạo ra hình ảnh PDF417 với kích thước chính xác bạn cần, sẵn sàng cho quá trình xử lý tiếp theo.

## Những gì bạn sẽ học

* Cài đặt và tham chiếu thư viện Aspose.BarCode.
* Tạo một PDF417 barcode generator và chỉ định văn bản được mã hoá.
* **Set barcode size** bằng cách cấu hình X‑dimension và số cột.
* Kích hoạt chế độ compact (truncated) để thu nhỏ ký hiệu.
* Lưu kết quả dưới dạng tệp PNG.
* Xử lý các vấn đề thường gặp như mã không đọc được và hình ảnh quá lớn.

### Yêu cầu trước

* .NET 6.0 hoặc mới hơn (API cũng hoạt động với .NET Framework 4.6+).
* Kiến thức cơ bản về C# và Visual Studio (hoặc bất kỳ IDE C# nào).
* Giấy phép Aspose.BarCode hợp lệ (bản dùng thử miễn phí hoạt động cho việc thử nghiệm).

> **Pro tip:** Nếu bạn dự định tạo nhiều mã vạch trong một vòng lặp, hãy tái sử dụng một thể hiện `BarcodeGenerator` duy nhất và chỉ thay đổi thuộc tính `CodeText`. Điều này giảm việc cấp phát bộ nhớ.

## Tạo mã vạch PDF417 với Aspose.BarCode

Bước đầu tiên là khởi tạo `BarcodeGenerator` cho ký hiệu PDF417. Đối tượng này là điểm vào cho tất cả các thao tác mã vạch.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.Pdf417,          // Symbology
    "Sample text for PDF417");   // Data to encode
```

*Why this matters*: `EncodeTypes.Pdf417` cho thư viện biết sử dụng chuẩn PDF417, hỗ trợ khối lượng dữ liệu lớn và sửa lỗi. Hàm khởi tạo cũng nhận dữ liệu bạn muốn mã hoá, loại bỏ nhu cầu gán `CodeText` riêng sau này.

## Đặt kích thước mã vạch và số cột

Các ký hiệu PDF417 bao gồm các hàng và cột của các mô-đun hình chữ nhật nhỏ. Kiểm soát độ rộng mô-đun (X‑dimension) và số cột cho phép bạn tinh chỉnh kích thước tổng thể.

```csharp
// Step 2: Adjust the module size (X‑dimension) – 2 pixels per module
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Define the number of columns for the PDF417 code
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 3;
```

*Explanation*:  
* **X‑dimension** (`Pixels`) xác định độ rộng của mỗi mô-đun. Giá trị nhỏ hơn tạo mã vạch chặt hơn, trong khi giá trị lớn hơn tăng khả năng đọc trên máy quét độ phân giải thấp.  
* **Columns** kiểm soát bố cục ngang. Ít cột hơn làm mã vạch cao hơn; nhiều cột hơn làm nó rộng hơn. Điều chỉnh hai thiết lập này cùng nhau để đạt được **set barcode size** chính xác mà bạn cần.

## Kích hoạt chế độ compact để có mã vạch nhỏ hơn

PDF417 bao gồm chế độ “compact” (hoặc truncated) loại bỏ phần đệm không cần thiết và giảm diện tích tổng thể. Điều này đặc biệt hữu ích khi bạn có không gian màn hình hạn chế.

```csharp
// Step 4: Enable compact mode to truncate the barcode data
barcodeGenerator.Parameters.Barcode.Pdf417.Truncate = true;
```

*Why enable truncation?*  
Khi `Truncate` là `true`, trình tạo bỏ qua mẫu dừng và một số codeword sửa lỗi không cần thiết cho hầu hết các kịch bản quét. Hình ảnh kết quả giảm khoảng 15‑20 % mà không làm mất tính toàn vẹn dữ liệu cho các trường hợp sử dụng thông thường.

## Lưu mã vạch dưới dạng ảnh PNG

Sau khi cấu hình kích thước và chế độ, ghi mã vạch ra đĩa. PNG là định dạng không mất dữ liệu, đảm bảo các cạnh mô-đun vẫn sắc nét.

```csharp
// Step 5: Save the generated barcode as a PNG image
barcodeGenerator.Save(
    "YOUR_DIRECTORY/CompactPdf417.png",
    BarCodeImageFormat.Png);
```

Tệp `CompactPdf417.png` sẽ chứa một ký hiệu PDF417 sắc nét phù hợp với kích thước bạn đã đặt ở các bước trước.

### Kết quả mong đợi

Mở PNG đã lưu sẽ hiển thị một mã vạch PDF417 theo chiều dọc gồm ba cột, mỗi mô-đun rộng 2 px, và tổng kích thước khoảng **120 × 240 px** (rộng × cao). Quét hình ảnh bằng bất kỳ trình đọc PDF417 tiêu chuẩn nào sẽ trả về văn bản gốc “Sample text for PDF417”.

## Những lỗi thường gặp và cách tránh

| Triệu chứng | Nguyên nhân có thể | Cách khắc phục |
|------------|--------------------|----------------|
| Mã vạch không đọc được | X‑dimension quá nhỏ đối với máy quét | Tăng `XDimension.Pixels` lên 3 hoặc 4 |
| Hình ảnh quá rộng đối với UI | Quá nhiều cột được đặt | Giảm `Pdf417.Columns` hoặc bật `Truncate` |
| Exception `ArgumentOutOfRangeException` | Số cột âm hoặc bằng 0 | Đảm bảo `Columns` là số nguyên dương (tối thiểu 1) |
| Tệp PNG rỗng | Đường dẫn đầu ra không tồn tại hoặc thiếu quyền ghi | Kiểm tra thư mục tồn tại và ứng dụng có quyền ghi |

> **Pro tip:** Sử dụng `barcodeGenerator.ValidateParameters()` trước khi gọi `Save()` để phát hiện lỗi cấu hình sớm.

## Ví dụ đầy đủ, có thể chạy

Dưới đây là một chương trình console tự chứa, bao gồm tất cả các bước ở trên. Sao chép nó vào một dự án C# mới, khôi phục gói NuGet Aspose.BarCode, và chạy để xem kết quả.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with the data to encode
            var generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample text for PDF417");

            // Set module width (X‑dimension) – 2 px per module
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Choose a small number of columns to keep the barcode compact
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable truncation for a smaller image
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Optional: validate parameters before saving
            generator.ValidateParameters();

            // Save as PNG
            const string outputPath = "CompactPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

**Running the program** tạo ra `CompactPdf417.png` trong thư mục làm việc của tệp thực thi. Quét hình ảnh bằng một ứng dụng di động (ví dụ, “Barcode Scanner”) để xác nhận rằng văn bản đã mã hoá khớp với chuỗi nguồn.

## Các bước tiếp theo và các chủ đề liên quan

* **Increase error correction level** – điều chỉnh `Pdf417.ErrorLevel` cho môi trường có quét nhiễu.  
* **Change orientation** – đặt `Pdf417.Rotate` thành `RotationAngle.Rotate90` nếu bạn cần bố cục ngang.  
* **Embed the barcode in a PDF** – kết hợp Aspose.PDF với Aspose.BarCode để chèn hình ảnh trực tiếp vào tài liệu.  
* **Generate other 2‑D barcodes** – lớp `BarcodeGenerator` tương tự hỗ trợ DataMatrix, QR và Aztec; chỉ cần thay `EncodeTypes.Pdf417` bằng ký hiệu mong muốn.

Bằng cách thành thạo các kỹ thuật **generate PDF417 barcode**, bạn có thể tự động hoá việc bán vé, dán nhãn tồn kho, và truyền dữ liệu an toàn trên nhiều ứng dụng .NET.

## Kết luận

Bây giờ bạn đã biết cách **generate PDF417 barcode** trong C#, chính xác **set barcode size**, cấu hình số cột, bật chế độ compact, và lưu kết quả dưới dạng PNG. Áp dụng các thiết lập này để phù hợp với bất kỳ ràng buộc UI hoặc yêu cầu quét nào, và mở rộng phương pháp sang các định dạng mã vạch khác khi cần. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ hoạt động với giải thích từng bước để giúp bạn thành thạo các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch PDF417 – Mã hoá PDF417 Compact](/barcode/english/net/compact-pdf417-encoding/)
- [Cách tạo mã vạch – PDF417 Compact với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Cách tạo mã vạch DataMatrix bằng Aspose.BarCode cho .NET – Hướng dẫn từng bước](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}