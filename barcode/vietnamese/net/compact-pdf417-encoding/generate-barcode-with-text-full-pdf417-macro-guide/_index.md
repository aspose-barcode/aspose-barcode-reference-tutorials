---
category: general
date: 2026-07-18
description: Tạo mã vạch kèm văn bản bằng Aspose.BarCode cho .NET. Tìm hiểu cách tạo
  mã vạch PDF417, thiết lập các tùy chọn macro và xuất hình ảnh PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode with text
- how to generate pdf417
language: vi
lastmod: 2026-07-18
og_description: Tạo mã vạch với văn bản trong C# nhanh chóng. Hướng dẫn từng bước
  này chỉ cách tạo mã vạch PDF417, cấu hình các thiết lập macro và lưu dưới dạng PNG.
og_image_alt: Screenshot of a generated barcode with text using Aspose.BarCode
og_title: Tạo mã vạch với văn bản – Tạo Macro PDF417 Master
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate barcode with text using Aspose.BarCode for .NET. Learn how
    to generate PDF417 barcodes, set macro options, and export PNG images.
  headline: Generate barcode with text – Full PDF417 Macro Guide
  type: TechArticle
tags:
- barcode generation
- PDF417
- Aspose.BarCode
title: Tạo mã vạch với văn bản – Hướng dẫn đầy đủ PDF417 Macro
url: /vi/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch với văn bản – Hướng dẫn đầy đủ PDF417 Macro

Bạn đã bao giờ tự hỏi **cách tạo PDF417** mã vạch mà cũng nhúng văn bản tùy chỉnh chưa? Trong hướng dẫn này, bạn sẽ thấy chính xác cách **tạo mã vạch với văn bản** bằng Aspose.BarCode cho .NET, và chúng tôi sẽ hướng dẫn qua mọi cài đặt cần thiết cho một ký hiệu Macro PDF417. Không có phần thừa, chỉ có một ví dụ hoàn chỉnh, có thể chạy được mà bạn có thể đưa vào dự án ngay hôm nay.

Chúng tôi sẽ đề cập tới:

* Gói NuGet cần thiết và các chỉ thị using.  
* Cách tạo trình tạo mã vạch bao gồm các ký tự Unicode.  
* Cài đặt kích thước module, số cột và các ID đặc thù cho macro.  
* Lưu kết quả dưới dạng tệp PNG và xác minh đầu ra.  

Khi kết thúc, bạn sẽ có một hình ảnh PNG sẵn sàng sử dụng của mã vạch Macro PDF417 mà bạn có thể nhúng vào hoá đơn, vé, hoặc bất kỳ tài liệu nào cần một đoạn có thể đọc bằng máy.

---

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

| Requirement | Reason |
|-------------|--------|
| **.NET 6.0** or later | Aspose.BarCode hỗ trợ .NET Standard 2.0+, vì vậy .NET 6 cung cấp môi trường chạy mới nhất. |
| **Visual Studio 2022** (or any C# IDE) | Để dễ dàng chỉnh sửa và gỡ lỗi. |
| **Aspose.BarCode for .NET** NuGet package | Thư viện thực sự tạo mã vạch. Cài đặt bằng `dotnet add package Aspose.BarCode`. |
| **Write permission** to the output folder | Phương thức `Save` cần ghi tệp PNG. |

Nếu bất kỳ mục nào trong số này bạn chưa quen, hãy dừng lại và chuẩn bị chúng—nếu không mã sẽ ném ra các ngoại lệ rõ ràng.

## Bước 1 – Cài đặt và nhập thư viện

Đầu tiên, thêm gói NuGet vào dự án của bạn:

```bash
dotnet add package Aspose.BarCode
```

Sau đó, đưa các namespace cần thiết vào phạm vi:

```csharp
using Aspose.BarCode.Generation;   // Core generation classes
using Aspose.BarCode;               // General utilities (optional)
```

> **Mẹo:** Nếu bạn đang sử dụng Visual Studio, nhấp chuột phải vào dự án → *Manage NuGet Packages* → tìm kiếm *Aspose.BarCode* và cài đặt phiên bản ổn định mới nhất.

## Bước 2 – Tạo trình tạo mã vạch với văn bản tùy chỉnh của bạn

*Task* chính là **tạo mã vạch với văn bản** chứa các ký tự đặc biệt như “Å” và “©”. Hàm khởi tạo nhận loại mã hoá và chuỗi dữ liệu thô:

```csharp
// Step 2: Initialise a Macro PDF417 generator with Unicode text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.MacroPdf417,            // Macro PDF417 type
    "Åspóse.Barcóde©");                 // Text to encode (Unicode supported)
```

Tại sao điều này quan trọng: `EncodeTypes.MacroPdf417` cho Aspose biết chúng ta muốn phiên bản macro, cho phép chia một thông điệp lớn thành nhiều ký hiệu. Chuỗi văn bản có thể là bất kỳ chuỗi UTF‑8 nào; Aspose xử lý việc chuyển đổi bên trong.

## Bước 3 – Điều chỉnh giao diện cơ bản (kích thước module)

“Module” của mã vạch là ô đen‑hoặc‑trắng nhỏ nhất. Đặt kích thước pixel của nó kiểm soát kích thước tổng thể của hình ảnh mà không thay đổi mật độ dữ liệu:

```csharp
// Step 3: Set module (X‑dimension) size to 2 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Nếu bạn cần hình ảnh lớn hơn để in, tăng giá trị này lên 4 hoặc 6. Chỉ cần nhớ rằng các module lớn hơn sẽ làm tăng kích thước PNG cuối cùng.

## Bước 4 – Cấu hình các tùy chọn đặc thù cho Macro PDF417

Macro PDF417 thêm hai định danh cho phép máy quét ghép nối nhiều ký hiệu lại với nhau. Thông thường bạn sẽ thiết lập:

| Property | What it does |
|----------|--------------|
| `Columns` | Số cột dữ liệu mỗi ký hiệu (ảnh hưởng đến chiều rộng). |
| `MacroPdf417FileID` | ID duy nhất cho toàn bộ tệp macro (phải ≤ 2³¹‑1). |
| `MacroPdf417SegmentID` | Chỉ mục của đoạn hiện tại (0‑254). |

Đây là đoạn mã:

```csharp
// Step 4: Define macro‑specific settings
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;                     // Narrower barcode
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;   // Consistent across all segments
barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // This is segment #12
```

**Lưu ý trường hợp đặc biệt:** `MacroPdf417FileID` phải giống nhau cho mọi đoạn trong cùng một tệp logic. Nếu bạn tạo nhiều đoạn, hãy tái sử dụng cùng một ID hoặc bạn sẽ có các ký hiệu không liên quan không thể ghép lại với nhau.

## Bước 5 – Lưu mã vạch dưới dạng hình ảnh PNG

Bây giờ mọi thứ đã được cấu hình, hãy ghi hình ảnh ra đĩa:

```csharp
// Step 5: Export the barcode to PNG
string outputPath = @"C:\Barcodes\MacroPdf417Main.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
```

Phương thức `Save` tự động tạo PNG, xử lý DPI và độ sâu màu cho bạn. Sau khi thực thi, mở tệp để thấy một hình như sau:

![Ví dụ tạo mã vạch với văn bản](/images/barcode-example.png){.center alt="Ví dụ tạo mã vạch với văn bản"}

Nếu bạn không thấy mã vạch, hãy kiểm tra lại rằng thư mục tồn tại và ứng dụng của bạn có quyền ghi.

## Ví dụ đầy đủ, có thể chạy ngay

Sao chép toàn bộ đoạn mã dưới đây vào một ứng dụng console mới (`dotnet new console`) và chạy nó. Nó sẽ tạo PNG trong thư mục `C:\Barcodes` (đầu tiên hãy tạo thư mục).

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise generator with Unicode text
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MacroPdf417,
            "Åspóse.Barcóde©");

        // 2️⃣ Set module size (pixel density)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Macro‑PDF417 specific settings
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
        generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

        // 4️⃣ Export to PNG
        string path = @"C:\Barcodes\MacroPdf417Main.png";
        generator.Save(path, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {path}");
    }
}
```

**Kết quả mong đợi** (console):

```
Barcode saved to C:\Barcodes\MacroPdf417Main.png
```

Và PNG sẽ hiển thị một ký hiệu Macro PDF417 gọn gàng chứa văn bản “Åspóse.Barcóde©”.

## Câu hỏi thường gặp & Những bẫy thường gặp

| Question | Answer |
|----------|--------|
| *Tôi có thể sử dụng định dạng hình ảnh khác không?* | Chắc chắn—thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, hoặc `Gif`. PNG không mất dữ liệu, vì vậy chúng tôi mặc định sử dụng nó. |
| *Nếu tôi cần hơn một đoạn thì sao?* | Tạo một `BarcodeGenerator` mới cho mỗi đoạn, giữ `MacroPdf417FileID` giống nhau, và tăng `MacroPdf417SegmentID` (0‑254). |
| *Văn bản của tôi chứa emoji—liệu chúng có hoạt động không?* | Aspose.BarCode hỗ trợ UTF‑8, vì vậy hầu hết các emoji đều ổn. Chỉ cần đảm bảo máy quét mục tiêu có thể giải mã chúng; nhiều máy quét công nghiệp chỉ xử lý dữ liệu chữ và số. |
| *Mã vạch quá rộng so với nhãn của tôi.* | Giảm `Columns` hoặc tăng kích thước module. Ít cột hơn sẽ tạo ký hiệu hẹp hơn, nhưng có thể yêu cầu máy in DPI cao hơn. |
| *Tôi có cần giấy phép không?* | Giấy phép đánh giá miễn phí hoạt động cho việc thử nghiệm, nhưng nó sẽ thêm một watermark nhỏ. Đối với sản xuất, mua giấy phép để loại bỏ watermark và mở khóa đầy đủ tính năng. |

## Các bước tiếp theo

Bây giờ bạn đã biết **cách tạo PDF417** mã vạch với văn bản tùy chỉnh, bạn có thể muốn:

* **Giải mã** mã vạch trong ứng dụng di động bằng `BarCodeReader` của Aspose.BarCode.  
* **Kết hợp** nhiều đoạn macro thành một tài liệu PDF duy nhất để in hàng loạt.  
* **Khám phá các ký hiệu khác** (QR, DataMatrix) với các mẫu tham số tương tự.  
* **Điều chỉnh mức độ sửa lỗi** qua `Pdf417.ErrorCorrectionLevel` cho môi trường khắc nghiệt.  

Mỗi chủ đề này dựa trên cùng các khái niệm cốt lõi mà bạn vừa học, vì vậy bạn sẽ thấy quá trình chuyển đổi suôn sẻ.

## Kết luận

Chúng tôi đã hướng dẫn qua một giải pháp hoàn chỉnh, đầu‑tới‑cuối cho phép bạn **tạo mã vạch với văn bản** và, cụ thể, **cách tạo ký hiệu macro PDF417** bằng Aspose.BarCode cho .NET. Bằng cách thiết lập kích thước X, số cột và các ID macro, bạn có toàn quyền kiểm soát kích thước, bố cục và việc xử lý đa‑đoạn. PNG kết quả có thể được in, nhúng vào PDF, hoặc gửi tới máy quét mà không cần chuyển đổi thêm.

Hãy thử nghiệm, điều chỉnh các tham số, và để mã vạch phục vụ cho trường hợp kinh doanh của bạn. Nếu gặp khó khăn, tài liệu của Aspose và diễn đàn cộng đồng là những nguồn tài nguyên hỗ trợ tuyệt vời. Chúc bạn lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao phủ các chủ đề liên quan chặt chẽ, dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoạt động đầy đủ với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch PDF417 – Mã hoá PDF417 Compact](/barcode/english/net/compact-pdf417-encoding/)
- [Cách tạo mã vạch DataMatrix với Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [Cách tạo mã vạch - Các loại mã vạch một chiều](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}