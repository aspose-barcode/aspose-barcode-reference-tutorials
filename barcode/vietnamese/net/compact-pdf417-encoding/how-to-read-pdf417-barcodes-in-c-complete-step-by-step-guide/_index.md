---
category: general
date: 2026-09-22
description: Học cách đọc mã vạch PDF417 trong C# với một ví dụ đầy đủ về trình đọc
  mã vạch. Hướng dẫn này cho bạn thấy cách đọc hình ảnh mã vạch trong C# một cách
  nhanh chóng và đáng tin cậy.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: vi
lastmod: 2026-09-22
og_description: Cách đọc mã vạch PDF417 trong C# bằng ví dụ trình đọc mã vạch ngắn
  gọn. Theo dõi hướng dẫn để giải mã hình ảnh Macro PDF417 và trích xuất siêu dữ liệu.
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: Cách đọc mã vạch PDF417 trong C# – ví dụ đầy đủ về trình đọc mã vạch
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: Cách đọc mã vạch PDF417 trong C# – hướng dẫn chi tiết từng bước
url: /vi/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đọc mã vạch PDF417 trong C# – hướng dẫn chi tiết từng bước

Nếu bạn cần **cách đọc pdf417** trong một ứng dụng .NET, hướng dẫn này sẽ cho bạn mã nguồn chính xác và lý do cần thiết. Sau hai câu đầu tiên, bạn sẽ biết cách đọc ảnh mã vạch C# bằng lớp `BarCodeReader` phổ biến, và sẽ có một ví dụ sẵn sàng chạy để trích xuất mọi siêu dữ liệu Macro PDF417.

Đọc mã vạch PDF417 là yêu cầu thường gặp khi xử lý nhãn vận chuyển, thẻ lên máy bay, hoặc tài liệu bảo mật. Bài học này bao gồm mọi thứ từ việc thiết lập trình đọc đến xử lý các trường hợp đặc biệt, giúp bạn tích hợp việc quét mã vạch một cách tự tin.

## Những gì bạn sẽ đạt được

- Giải mã một tệp ảnh Macro PDF417.
- In thông tin cơ bản của mã vạch (loại và văn bản).
- Truy cập tất cả các trường mở rộng Macro PDF417 như file ID, số đoạn, và timestamp.
- Hiểu các bẫy thường gặp khi làm việc với các mã PDF417 đa đoạn.

**Yêu cầu trước**

- .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+).
- Tham chiếu tới SDK mã vạch cung cấp `BarCodeReader`, `DecodeType` và `BarCodeResult` (ví dụ: Aspose.BarCode, Dynamsoft, hoặc bất kỳ thư viện nào có API tương tự).
- Một tệp ảnh (`ExtPDF417Meta.png`) chứa mã vạch Macro PDF417.

> **Mẹo chuyên nghiệp:** Đặt ảnh vào một thư mục tương đối với thư mục gốc dự án và đặt thuộc tính **Copy to Output Directory** thành *Copy if newer* để đường dẫn hoạt động khi gỡ lỗi.

![How to read PDF417 barcode using C#](https://example.com/placeholder-image.png)

## Cách đọc mã vạch PDF417 trong C# – mã hoàn chỉnh

Dưới đây là một chương trình tự chứa mà bạn có thể dán vào ứng dụng console. Nó tạo một trình đọc mã vạch, lặp qua mọi kết quả đã giải mã, và in cả các trường chuẩn và mở rộng của Macro PDF417.

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
    }
}
```

### Tại sao mỗi bước lại quan trọng

1. **Tạo trình đọc với `DecodeType.MacroPdf417`** – Macro PDF417 là một biến thể đặc biệt có thể chứa siêu dữ liệu ở mức tệp. Việc chỉ định kiểu giải mã đảm bảo SDK phân tích các trường bổ sung này thay vì xem mã như một PDF417 thông thường.
2. **Lặp qua `ReadBarCodes()`** – Một ảnh có thể chứa hơn một mã vạch (ví dụ: một QR code bên cạnh PDF417). Vòng lặp bảo đảm bạn nắm bắt mọi kết quả.
3. **In `CodeTypeName` và `CodeText`** – Đây là các thuộc tính được sử dụng thường nhất; chúng cung cấp tên ký hiệu và dữ liệu có thể đọc được bởi con người.
4. **Truy cập `Extended.Pdf417`** – Đối tượng `Extended` chỉ xuất hiện với các kiểu giải mã liên quan tới PDF417. Mỗi thuộc tính ánh xạ trực tiếp tới đặc tả Macro PDF417, cho phép bạn tái tạo lại tệp gốc hoặc xác thực thứ tự các đoạn.

## Các biến thể phổ biến và trường hợp đặc biệt

### Đọc mã vạch PDF417 không phải macro

Nếu các ảnh nguồn của bạn chứa các mã PDF417 thông thường (không có siêu dữ liệu macro), thay `DecodeType.MacroPdf417` bằng `DecodeType.Pdf417`. Phần còn lại của mã vẫn giống y hệt, nhưng khối `Extended.Pdf417` sẽ rỗng vì các trường đó không tồn tại.

### Xử lý PDF đa đoạn

Macro PDF417 có thể chia một tài liệu lớn thành nhiều đoạn mã vạch. Để ghép lại tệp gốc, bạn phải:

1. Thu thập `Pdf417MacroSegmentID` của mỗi đoạn.
2. Sắp xếp các đoạn theo ID của chúng.
3. Xác minh `Pdf417MacroSegmentsCount` khớp với số đoạn đã nhận.
4. Nối `CodeText` của mỗi đoạn theo thứ tự.
5. Tùy chọn, xác thực `Pdf417MacroChecksum`.

Dưới đây là một đoạn mã ngắn gọn minh họa logic ghép lại:

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### Xử lý ảnh bị hỏng

- **Độ tương phản thấp** – Tăng tiền xử lý ảnh (ví dụ: cân bằng histogram) trước khi truyền cho `BarCodeReader`.
- **Xoay** – Sử dụng `barcodeReader.SetRotateAngle(90)` hoặc bật tự động xoay nếu SDK hỗ trợ.
- **Quét một phần** – Đảm bảo độ phân giải ảnh ít nhất 300 dpi; nếu không SDK có thể bỏ lỡ các đoạn nhỏ.

## ví dụ trình đọc mã vạch c# – các thực tiễn tốt nhất

| Thực tiễn | Lý do |
|----------|--------|
| **Dispose trình đọc bằng `using`** | Đảm bảo tài nguyên gốc được giải phóng kịp thời, ngăn rò rỉ bộ nhớ. |
| **Kiểm tra `result.Extended` không null** | Một số SDK trả về `null` cho các mã không phải macro; kiểm tra tránh `NullReferenceException`. |
| **Ghi log `Pdf417MacroFileID`** | Định danh này là duy nhất cho mỗi tệp và hữu ích cho việc truy vết. |
| **Bao bọc quá trình giải mã trong try/catch** | Lỗi I/O (thiếu tệp) hoặc định dạng không hỗ trợ sẽ ném ngoại lệ cần được xử lý một cách mềm mại. |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## Kết quả mong đợi

Chạy toàn bộ chương trình với tệp `ExtPDF417Meta.png` được định dạng đúng sẽ cho ra kết quả tương tự như:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Nếu ảnh chứa nhiều đoạn, vòng lặp sẽ in siêu dữ liệu của mỗi đoạn theo thứ tự.

## Kết luận

Bạn đã biết **cách đọc pdf417** trong C# và có một **ví dụ trình đọc mã vạch c#** để trích xuất mọi trường Macro PDF417. Giải pháp bao gồm giải mã cơ bản, trích xuất siêu dữ liệu, ghép lại đa đoạn và xử lý lỗi, cung cấp nền tảng sẵn sàng cho bất kỳ quy trình xử lý tài liệu nào.

### Các bước tiếp theo

- Khám phá các kỹ thuật **read barcode image C#** cho các ký hiệu khác (QR, DataMatrix) bằng cùng API `BarCodeReader`.
- Tích hợp trình giải mã mã vạch vào dịch vụ ASP.NET Core để xử lý tải lên ngay lập tức.
- Thử nghiệm các thư viện tiền xử lý ảnh (ví dụ: `OpenCvSharp`) để nâng cao tỷ lệ thành công trên các quét chất lượng thấp.

Chúc lập trình vui vẻ, và hãy tùy chỉnh ví dụ sao cho phù hợp với trường hợp sử dụng cụ thể của bạn!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong bài này. Mỗi tài nguyên bao gồm mã mẫu đầy đủ với các giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}