---
category: general
date: 2026-10-12
description: Học cách tạo mã vạch micro PDF417 và chuyển mã vạch sang PNG bằng C#.
  Hướng dẫn từng bước với mã đầy đủ và các mẹo.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro PDF417 barcode
- convert barcode to PNG
- micro PDF417 C# example
- GS1 micro PDF417 generation
- barcode image settings
language: vi
lastmod: 2026-10-12
og_description: Tạo mã vạch micro PDF417 và chuyển mã vạch sang PNG bằng C#. Hãy theo
  hướng dẫn đầy đủ này để tạo cả phiên bản tiêu chuẩn và GS1.
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: Tạo mã vạch micro PDF417 và chuyển đổi sang PNG – Hướng dẫn C#
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn to create micro PDF417 barcode and convert barcode to PNG using
    C#. Step‑by‑step guide with full code and tips.
  headline: How to create micro PDF417 barcode and convert it to PNG in C#
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cách tạo mã vạch micro PDF417 và chuyển đổi sang PNG trong C#
url: /vi/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-convert-it-to-png-in/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch micro PDF417 và chuyển đổi nó sang PNG trong C#

Nếu bạn cần **tạo mã vạch micro PDF417** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Bạn sẽ thấy một ví dụ hoàn chỉnh, có thể chạy được, tạo cả mã vạch Micro PDF417 tiêu chuẩn và phiên bản tuân thủ GS1, sau đó **chuyển mã vạch sang PNG** để sử dụng tiếp như in ấn hoặc hiển thị trên web.

Việc tạo mã vạch không chỉ đơn giản là gọi một phương thức—việc chọn kích thước mô-đun, số cột và định dạng mã hoá phù hợp quyết định độ tin cậy khi quét. Khi kết thúc hướng dẫn này, bạn sẽ hiểu tại sao mỗi thiết lập quan trọng và cách điều chỉnh chúng cho dự án của mình.

## Yêu cầu trước

| Yêu cầu | Lý do |
|-------------|--------|
| .NET 6.0 SDK or later | Cung cấp môi trường chạy cho ứng dụng console C# |
| Visual Studio 2022 (or any C# IDE) | Giúp việc chỉnh sửa và gỡ lỗi dễ dàng hơn |
| **Aspose.BarCode for .NET** NuGet package | Cung cấp các lớp `BarcodeGenerator`, `EncodeTypes`, và `BarCodeImageFormat` |
| Write permission to the output folder | Cần thiết cho các lệnh `Save` tạo tệp PNG |

Bạn có thể thêm gói Aspose.BarCode thông qua CLI:

```bash
dotnet add package Aspose.BarCode
```

## Bước 1: Thiết lập dự án console tối thiểu

Tạo một dự án console mới và tham chiếu thư viện mã vạch. Tệp `Program.cs` dưới đây chứa toàn bộ mã bạn cần; không yêu cầu tệp bên ngoài.

```csharp
using System;
using Aspose.BarCode.Generation;   // Core barcode generation classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace MicroPdf417Demo
{
    internal class Program
    {
        static void Main()
        {
            // Define the folder where PNG files will be saved
            string outputFolder = Environment.CurrentDirectory;

            // ------------------------------------------------------------
            // 1️⃣ Create a Micro PDF417 barcode generator with plain data
            // ------------------------------------------------------------
            BarcodeGenerator microGen = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,          // Micro PDF417 symbology
                "Micro data");                    // Simple alphanumeric payload

            // ------------------------------------------------------------
            // 2️⃣ Adjust the X dimension (module size) and set column count
            // ------------------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // A value of 2 pixels gives a compact yet readable barcode.
            microGen.Parameters.Barcode.XDimension.Pixels = 2;

            // For Micro PDF417 you can limit the number of columns.
            // Four columns keep the barcode small enough for labels.
            microGen.Parameters.Barcode.Pdf417.Columns = 4;

            // ------------------------------------------------------------
            // 3️⃣ Convert barcode to PNG and save the image
            // ------------------------------------------------------------
            string microPath = System.IO.Path.Combine(outputFolder, "MicroPdf417.png");
            microGen.Save(microPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Standard Micro PDF417 saved to: {microPath}");

            // ------------------------------------------------------------
            // 4️⃣ Create a GS1 Micro PDF417 barcode with AI‑encoded data
            // ------------------------------------------------------------
            // GS1 syntax requires Application Identifiers (AIs) wrapped in parentheses.
            // Example: (01) – GTIN, (21) – serial number.
            BarcodeGenerator gs1MicroGen = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(21)ABC123");

            // ------------------------------------------------------------
            // 5️⃣ Set the X dimension for the GS1 barcode (same as step 2)
            // ------------------------------------------------------------
            gs1MicroGen.Parameters.Barcode.XDimension.Pixels = 2;

            // ------------------------------------------------------------
            // 6️⃣ Convert barcode to PNG and save the GS1 image
            // ------------------------------------------------------------
            string gs1Path = System.IO.Path.Combine(outputFolder, "GS1MicroPdf417.png");
            gs1MicroGen.Save(gs1Path, BarCodeImageFormat.Png);
            Console.WriteLine($"GS1 Micro PDF417 saved to: {gs1Path}");

            // End of demo
            Console.WriteLine("Barcode generation complete.");
        }
    }
}
```

### Tại sao mỗi dòng lại quan trọng

* **`EncodeTypes.MicroPdf417` vs `EncodeTypes.Gs1MicroPdf417`** – Dòng đầu tạo một mã vạch Micro PDF417 đơn giản, trong khi dòng thứ hai tuân theo tiêu chuẩn GS1, nhúng các Application Identifiers (AIs). Chọn dựa trên việc hệ thống downstream của bạn có yêu cầu dữ liệu GS1 hay không.
* **`XDimension.Pixels = 2`** – Kiểm soát độ rộng mô-đun. Giá trị nhỏ hơn tạo hình ảnh dày đặc hơn nhưng có thể không đọc được trên máy quét độ phân giải thấp. Hai pixel là giá trị mặc định an toàn cho hầu hết máy in nhãn.
* **`Pdf417.Columns = 4`** – Micro PDF417 cho phép giới hạn số cột, giảm chiều rộng tổng thể. Bốn cột giữ mã vạch gọn gàng mà không làm giảm khả năng chứa dữ liệu cho các payload ngắn.
* **`BarCodeImageFormat.Png`** – PNG giữ chất lượng không mất dữ liệu, rất quan trọng cho độ rõ nét của mã vạch. Đó là lý do chúng tôi **chuyển mã vạch sang PNG** thay vì JPEG.

## Bước 2: Chạy chương trình và xác minh đầu ra

1. Xây dựng dự án: `dotnet build`.
2. Thực thi: `dotnet run`.

Bạn sẽ thấy các thông báo console tương tự như:

```
Standard Micro PDF417 saved to: C:\Path\To\Project\MicroPdf417.png
GS1 Micro PDF417 saved to: C:\Path\To\Project\GS1MicroPdf417.png
Barcode generation complete.
```

Mở các tệp PNG đã tạo bằng bất kỳ trình xem ảnh nào. Cả hai hình ảnh đều hiển thị mã vạch sắc nét, độ tương phản cao, sẵn sàng để quét.

### Kết quả hình ảnh mong đợi

| Loại mã vạch | Hình dạng |
|--------------|------------|
| **Micro PDF417** | Mẫu hình chữ nhật nhỏ với 4 cột, có thể đọc được bởi hầu hết máy quét mã vạch 2‑D. |
| **GS1 Micro PDF417** | Cùng kích thước nhưng mã hoá các GS1 AI; máy quét hiểu GS1 sẽ trả về GTIN và số serial. |

Nếu máy quét không đọc được hình ảnh, hãy thử tăng `XDimension.Pixels` lên **3** hoặc **4**, hoặc giảm số cột cho Micro PDF417 tiêu chuẩn.

## Những lỗi thường gặp và cách tránh

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------|-----|
| Mã vạch mờ sau khi in | Cài đặt máy in DPI thấp | Xuất PNG ở 300 dpi hoặc cao hơn, hoặc để driver máy in xử lý việc phóng to/thu nhỏ. |
| Máy quét trả về “dữ liệu không hợp lệ” | Định dạng GS1 AI thiếu hoặc sai | Đảm bảo mỗi AI được bao trong dấu ngoặc và tuân theo quy chuẩn GS1 (ví dụ, `(01)` cho GTIN‑14). |
| Tệp ảnh không được tạo | Thư mục đầu ra không có quyền ghi | Chạy chương trình với quyền nâng cao hoặc chọn thư mục như `Environment.GetFolderPath(Environment.SpecialFolder.MyDocuments)`. |
| Mã vạch quá lớn cho nhãn | Số cột mặc định quá cao | Giảm `Pdf417.Columns` (ví dụ, xuống **3**) hoặc tăng `XDimension` để thu nhỏ kích thước tổng thể. |

## Mở rộng ví dụ

* **Các định dạng ảnh khác** – Thay `BarCodeImageFormat.Png` bằng `Jpeg` hoặc `Bmp` nếu quy trình của bạn yêu cầu. PNG vẫn là lựa chọn tốt nhất cho chất lượng không mất dữ liệu.
* **Dữ liệu động** – Truyền dữ liệu nhập từ người dùng hoặc giá trị từ cơ sở dữ liệu vào hàm khởi tạo `BarcodeGenerator` để tạo mã vạch ngay lập tức.
* **Tạo hàng loạt** – Đặt logic tạo mã trong một vòng lặp đọc các dòng từ tệp CSV và lưu mỗi mã vạch với tên tệp duy nhất.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch micro PDF417** trong C# và **chuyển mã vạch sang PNG** cho cả các kịch bản tiêu chuẩn và tuân thủ GS1. Mã nguồn hoàn chỉnh, có thể chạy được minh họa các thiết lập quan trọng—kích thước X, số cột và kiểu mã hoá—để bạn có thể áp dụng giải pháp này cho bất kỳ dự án .NET nào cần mã vạch 2‑D gọn gàng, chất lượng cao.

*Bước tiếp theo*: khám phá các ký hiệu khác được Aspose.BarCode hỗ trợ (ví dụ, QR, DataMatrix), thử nghiệm các giá trị `XDimension` khác nhau cho in độ phân giải cao, hoặc tích hợp các PNG đã tạo vào một web API cung cấp mã vạch theo yêu cầu.

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoàn chỉnh, hoạt động kèm theo giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch micro pdf417 trong C# và lưu dưới dạng PNG](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-and-save-it-as-png/)
- [Tạo PNG mã vạch trong C# – hướng dẫn đầy đủ về GS1 Micro PDF417](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [Tạo Mã Vạch Micro PDF417 trong C# – Hướng Dẫn Toàn Diện](/barcode/english/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}