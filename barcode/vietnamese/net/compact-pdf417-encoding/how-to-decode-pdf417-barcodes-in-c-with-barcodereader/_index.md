---
category: general
date: 2026-09-07
description: Học cách giải mã mã vạch PDF417 trong C# bằng BarCodeReader. Hướng dẫn
  từng bước này cũng giải thích cách đọc dữ liệu PDF417 một cách hiệu quả.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: vi
lastmod: 2026-09-07
og_description: Cách giải mã mã vạch PDF417 trong C# bằng BarCodeReader. Hãy theo
  dõi hướng dẫn này để học cách đọc dữ liệu PDF417 và trích xuất các trường MacroPdf417.
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: Cách giải mã mã vạch PDF417 trong C# – hướng dẫn đầy đủ
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: Cách giải mã mã vạch PDF417 trong C# bằng BarCodeReader
url: /vi/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách giải mã mã vạch PDF417 trong C# với BarCodeReader

Nếu bạn cần **cách giải mã PDF417** trong một ứng dụng .NET, hướng dẫn này sẽ dẫn bạn qua toàn bộ quá trình. Bạn cũng sẽ khám phá **cách đọc dữ liệu PDF417** như file MacroPdf417 và các định danh segment, tất cả chỉ với vài dòng C#.

Giải mã PDF417 thường gặp khi làm việc với vé giao thông, giấy phép lái xe, hoặc nhãn vận chuyển. Khi kết thúc tutorial này, bạn sẽ có một chương trình console có thể chạy được, in ra mọi trường MacroPdf417 mà GroupDocs.Barcode SDK cung cấp.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc mới hơn (mã sẽ biên dịch với .NET Core và .NET Framework)
* Visual Studio 2022 hoặc bất kỳ IDE nào hỗ trợ C#
* Gói NuGet **GroupDocs.Barcode** (`GroupDocs.Barcode` ≥ 23.3)
* Một file ảnh chứa mã vạch Macro PDF417 (ví dụ, `ExtPDF417Meta.png`)

> **Mẹo chuyên nghiệp:** Cài đặt gói qua CLI:  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## Cách giải mã mã vạch PDF417 trong C#

Các phần sau chia giải pháp thành các bước logic. Mỗi bước bao gồm đoạn mã chính xác bạn cần và một giải thích ngắn gọn về lý do quan trọng.

### Bước 1: Chuẩn bị dự án và nhập namespace

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*Vì sao?*  
`GroupDocs.Barcode` cung cấp lớp `BarCodeReader`, trong khi `GroupDocs.Barcode.Common` chứa enumeration `DecodeType` cần thiết cho việc giải mã PDF417.

### Bước 2: Định nghĩa đường dẫn tới ảnh

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*Vì sao?*  
Trình đọc làm việc với bất kỳ định dạng ảnh nào được .NET hỗ trợ (`.png`, `.jpg`, `.bmp`). Cung cấp đúng đường dẫn giúp SDK xác định được file.

### Bước 3: Khởi tạo trình đọc mã vạch cho việc giải mã MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*Vì sao?*  
`DecodeType.MacroPdf417` báo cho SDK tìm định dạng Macro PDF417 mở rộng, chứa siêu dữ liệu bổ sung như ID file và segment. Sử dụng câu lệnh `using` đảm bảo các tài nguyên không quản lý được giải phóng kịp thời.

### Bước 4: Đọc mọi mã vạch có trong ảnh

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*Vì sao?*  
Một ảnh có thể chứa nhiều mã vạch. Phương thức `ReadBarCodes()` trả về một collection, cho phép bạn xử lý từng mã một cách riêng biệt.

### Bước 5: Lấy và hiển thị dữ liệu đặc thù của Macro PDF417

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*Vì sao?*  
Đối tượng `Extended.Pdf417` cung cấp tất cả các trường Macro PDF417 được định nghĩa trong tiêu chuẩn. In chúng ra giúp bạn xác nhận việc giải mã thành công và cung cấp dữ liệu cần thiết cho các quy trình tiếp theo.

### Ví dụ đầy đủ có thể chạy

Kết hợp các đoạn mã trên thành một file `Program.cs` duy nhất:

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**Kết quả console mong đợi** (giá trị sẽ khác tùy nội dung mã vạch):

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

Nếu ảnh không chứa mã vạch Macro PDF417, collection `ReadBarCodes()` sẽ rỗng và không có gì được in ra.

## Các biến thể thường gặp và trường hợp đặc biệt

| Tình huống | Cách điều chỉnh mã |
|-----------|----------------------|
| **PDF417 chuẩn (không phải macro)** | Thay `DecodeType.MacroPdf417` bằng `DecodeType.Pdf417`. Đối tượng `Extended.Pdf417` sẽ là `null`, vì vậy cần kiểm tra null trước khi truy cập. |
| **Nhiều ảnh** | Bao quanh việc khởi tạo reader bằng một vòng lặp `foreach (var path in imagePaths)`. |
| **Ảnh lớn** | Đặt `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` để giới hạn việc sử dụng bộ nhớ. |
| **Xử lý hàng loạt yêu cầu hiệu năng cao** | Tái sử dụng một thể hiện `BarCodeReader` duy nhất với `reader.SetImage(path)` thay vì tạo đối tượng mới cho mỗi file. |

## Danh sách kiểm tra khắc phục sự cố

* **Không có đầu ra:** Kiểm tra `imagePath` có trỏ tới file hợp lệ và ảnh thực sự chứa mã vạch PDF417. |
* **`Extended.Pdf417` trả về null:** Bạn có thể đã dùng `DecodeType.Pdf417` thay vì `MacroPdf417`. |
* **Ngoại lệ `FileNotFoundException`:** Đảm bảo thư mục làm việc trùng với đường dẫn hoặc sử dụng đường dẫn tuyệt đối. |
* **Điểm tin cậy (confidence) thấp:** Tăng chất lượng ảnh hoặc điều chỉnh các thiết lập `reader.Options.Quality`. |

## Kết luận

Bây giờ bạn đã biết **cách giải mã PDF417** trong C# và **cách đọc siêu dữ liệu PDF417** như ID file Macro, ID segment và timestamp. Ví dụ hoàn chỉnh minh họa cách khởi tạo `BarCodeReader`, chọn kiểu giải mã đúng, lặp qua kết quả và trích xuất mọi trường MacroPdf417 có sẵn.

Từ đây bạn có thể:

* Tích hợp dữ liệu đã trích xuất vào hệ thống logistics hoặc xác thực vé.
* Mở rộng ứng dụng console để ghi kết quả vào cơ sở dữ liệu hoặc file JSON.
* Khám phá các định dạng mã vạch khác được GroupDocs.Barcode hỗ trợ (QR, DataMatrix, Code128, v.v.) bằng cách thay đổi enumeration `DecodeType`.

Chúc bạn lập trình vui vẻ, và hãy thử nghiệm với các ảnh và cài đặt mã vạch khác nhau để thành thạo việc giải mã PDF417 trong các dự án .NET của mình!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode – Complete Programming Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}