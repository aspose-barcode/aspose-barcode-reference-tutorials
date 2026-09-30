---
category: general
date: 2026-08-03
description: Đọc mã vạch PDF417 từ một hình ảnh bằng C# BarCodeReader – một ví dụ
  hoàn chỉnh về trình đọc mã vạch, đồng thời cho thấy cách đọc nhiều mã vạch.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: vi
lastmod: 2026-08-03
og_description: Đọc mã vạch PDF417 nhanh chóng với ví dụ BarCodeReader bằng C#. Thực
  hiện theo hướng dẫn từng bước này để giải mã macro PDF417 và đọc nhiều mã vạch từ
  một hình ảnh.
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: Đọc mã vạch PDF417 trong C# – ví dụ đầy đủ về trình đọc mã vạch
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: Đọc mã vạch PDF417 bằng C# – ví dụ trình đọc mã vạch
url: /vi/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Đọc mã vạch PDF417 trong C# – ví dụ trình đọc mã vạch

Nếu bạn cần đọc dữ liệu mã vạch PDF417 từ một hình ảnh, hướng dẫn này sẽ chỉ cho bạn cách thực hiện bằng lớp **BarCodeReader** trong C#. Bạn sẽ học một ví dụ trình đọc mã vạch cũng hỗ trợ macro PDF417 và có thể đọc nhiều mã vạch trong một hình ảnh duy nhất.

Làm việc với mã vạch thường đồng nghĩa với việc phải xử lý các nguồn ảnh khác nhau, điều kiện ánh sáng thay đổi, và đôi khi dữ liệu tổng hợp như các đoạn macro PDF417. Hướng dẫn này bao phủ mọi thứ bạn cần để giải mã mã vạch PDF417, trích xuất các trường mở rộng, và xử lý nhiều mã vạch từ cùng một bức ảnh. Khi hoàn thành, bạn sẽ có một chương trình console có thể chạy được, đọc mã vạch từ tệp ảnh và in thông tin chi tiết ra console.

## Những gì bạn cần

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Phiên bản mới nhất của gói NuGet **Aspose.BarCode for .NET** (hoặc bất kỳ thư viện tương thích nào cung cấp `BarCodeReader` và `DecodeType.MacroPdf417`)  
* Một tệp hình ảnh chứa mã vạch PDF417 hoặc macro PDF417 (ví dụ sử dụng `ExtPDF417Meta.png`)  
* Một trình soạn thảo mã hoặc IDE như Visual Studio 2022  

Không cần dịch vụ bổ sung hay API bên ngoài.

## Cài đặt dự án để đọc mã vạch

1. **Tạo một dự án console mới**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **Thêm thư viện mã vạch**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **Sao chép hình ảnh mã vạch**  

   Đặt `ExtPDF417Meta.png` (hoặc bất kỳ hình ảnh nào chứa mã vạch PDF417) vào thư mục dự án.  
   Đối với hướng dẫn này, chúng tôi giả định tệp nằm ở `YOUR_DIRECTORY/ExtPDF417Meta.png`.

Dự án hiện đã sẵn sàng để biên dịch và chạy ví dụ trình đọc mã vạch.

## Cách đọc mã vạch PDF417 với BarCodeReader

Cốt lõi của giải pháp là một khối `using` tạo một thể hiện `BarCodeReader`, chỉ định `DecodeType.MacroPdf417`, và lặp qua mọi mã vạch được phát hiện. Đoạn mã dưới đây là một chương trình hoàn chỉnh, tự chứa, bạn có thể dán vào `Program.cs`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**Tại sao cách này hoạt động**:  

* `DecodeType.MacroPdf417` cho trình đọc biết tìm phần mở rộng macro của PDF417, chứa các siêu dữ liệu bổ sung như ID tệp, số đoạn và dấu thời gian.  
* Câu lệnh `using` đảm bảo các tài nguyên không quản lý (bộ xử lý tệp, bộ đệm giải mã gốc) được giải phóng kịp thời.  
* Vòng lặp `foreach` tự động xử lý **tất cả** các mã vạch mà hình ảnh chứa, đáp ứng yêu cầu *đọc nhiều mã vạch*.  

Khi bạn chạy chương trình (`dotnet run`), bạn sẽ thấy đầu ra tương tự như sau:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

Nếu hình ảnh chứa hơn một mã vạch PDF417, vòng lặp sẽ in một khối riêng cho mỗi mã vạch, qua đó minh họa cách **đọc nhiều mã vạch** từ một bức ảnh duy nhất.

## Đọc nhiều mã vạch từ một hình ảnh

Cùng một thể hiện `BarCodeReader` có thể giải mã nhiều loại mã vạch cùng lúc. Để mở rộng phạm vi từ chỉ macro PDF417 sang bất kỳ PDF417 nào (hoặc thậm chí QR, Code128, v.v.), điều chỉnh cờ `DecodeType`:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* là một bitmask, vì vậy bạn có thể kết hợp bất kỳ số lượng định dạng được hỗ trợ nào. Sự linh hoạt này biến đoạn mã thành một **ví dụ trình đọc mã vạch** hoạt động cho đa dạng trường hợp sử dụng, chẳng hạn như quét nhãn sản phẩm, vé, hoặc thẻ ID.

## Truy cập các trường macro PDF417 một cách an toàn

Macro PDF417 bổ sung một tập hợp phong phú các thuộc tính mở rộng. Tuy nhiên, không phải mọi mã vạch đều có đầy đủ các trường này. Việc truy cập một thuộc tính thiếu có thể gây ra `NullReferenceException`. Cách an toàn nhất là kiểm tra mỗi thuộc tính trước khi in:

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*Lý do quan trọng*: Trong các triển khai thực tế, bạn có thể nhận được mã vạch PDF417 thuần không có dữ liệu macro. Kiểm tra phòng thủ đảm bảo ứng dụng của bạn tiếp tục chạy mà không bị sập.

## Những vấn đề thường gặp và thực hành tốt nhất

| Vấn đề | Nguyên nhân | Giải pháp đề xuất |
|-------|----------------|-----------------|
| Đường dẫn hình ảnh không đúng | `BarCodeReader` ném ngoại lệ file‑not‑found trước khi thực hiện giải mã nào | Sử dụng `Path.Combine` và kiểm tra tệp tồn tại bằng `File.Exists` |
| Hình ảnh độ phân giải thấp | Bộ giải mã không thể xác định các cạnh mã vạch, dẫn đến không phát hiện được | Cung cấp độ phân giải tối thiểu 300 dpi để có kết quả đáng tin cậy |
| Mã vạch bị quay > 45° | Nhiều thư viện giả định hướng thẳng đứng | Bật `reader.RecognitionOptions.RotateImage = true` nếu |

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ, hoạt động với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách đọc mã vạch DataMatrix với Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Đọc mã vạch DataMatrix C# – Tạo chế độ DataMatrix (Tự động)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Đọc mã vạch từ hình ảnh – Thành thạo việc trích xuất vùng mã vạch trong Java với Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}